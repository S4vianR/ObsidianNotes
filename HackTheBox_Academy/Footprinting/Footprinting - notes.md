Mes: [[HackTheBox_Academy/Enero|Enero]]
Lista de cursos [[Lista de cursos]]

## Introduction
### Enumeration Methodology Notes

#### Overview

- **Purpose**: Establish a standardized methodology for complex processes like penetration testing to avoid omissions and ensure thoroughness.
- **Dynamic Nature**: Penetration testing is dynamic; thus, a static enumeration methodology is developed for both external and internal tests.
- **Structure**: The methodology consists of 6 layers, representing metaphorical boundaries in the enumeration process, divided into three levels:
    - Infrastructure-based enumeration
    - Host-based enumeration
    - OS-based enumeration

#### Layers of Enumeration Methodology

1. **Internet Presence**
    
    - **Description**: Identify the company's internet presence and externally accessible infrastructure.
    - **Information Categories**: Domains, subdomains, vHosts, ASN, netblocks, IP addresses, cloud instances, security measures.
2. **Gateway**
    
    - **Description**: Identify security measures protecting external and internal infrastructure.
    - **Information Categories**: Firewalls, DMZ, IPS/IDS, EDR, proxies, NAC, network segmentation, VPN, Cloudflare.
3. **Accessible Services**
    
    - **Description**: Identify accessible interfaces and services hosted externally or internally.
    - **Information Categories**: Service type, functionality, configuration, port, version, interface.
4. **Processes**
    
    - **Description**: Identify internal processes, sources, and destinations associated with services.
    - **Information Categories**: PID, processed data, tasks, source, destination.
5. **Privileges**
    
    - **Description**: Identify internal permissions and privileges for accessible services.
    - **Information Categories**: Groups, users, permissions, restrictions, environment.
6. **OS Setup**
    
    - **Description**: Identify internal components and system setup.
    - **Information Categories**: OS type, patch level, network configuration, OS environment, configuration files, sensitive private files.

#### Methodology Insights

- **Human Aspect**: The human element and OSINT information are excluded from the "Internet Presence" layer for simplicity.
- **Labyrinth Analogy**: The penetration test is likened to navigating a labyrinth, identifying gaps (vulnerabilities) to find entry points.
- **Limitations**: Time constraints limit the ability to identify all vulnerabilities; thorough understanding requires more extensive study.

#### Practical Application

- **External "Black Box" Testing**: Begins after fulfilling contract requirements, focusing on identifying targets in the "Internet Presence" layer.
- **Dynamic Approach**: The methodology is not a rigid step-by-step guide but a systematic approach that evolves with new tools and techniques.
- **Tool Utilization**: Various tools are available for information gathering, each with specific focuses, but the methodology remains a summary of systematic procedures rather than a list of tools.

## Infrastructure Based Enumeration

### Domain Information
#### Online Prescence
The first point of presence on the Internet may be the SSL certificate from the company's main website that we can examine.

Another source to find more subdomains is [Crt.sh](https://crt.sh). This source is Certificate Transparency logs. Certificate Transparency is a process that is intended to enable the verification of issued digital certificates for encrypted Internet connections.

##### Certificate Transparency
We can also output the results in JSON format.

```shell-session
R3ubenR4512@htb[/htb]$ curl -s https://crt.sh/\?q\=inlanefreight.com\&output\=json | jq .

[
  {
    "issuer_ca_id": 23451835427,
    "issuer_name": "C=US, O=Let's Encrypt, CN=R3",
    "common_name": "matomo.inlanefreight.com",
    "name_value": "matomo.inlanefreight.com",
    "id": 50815783237226155,
    "entry_timestamp": "2021-08-21T06:00:17.173",
    "not_before": "2021-08-21T05:00:16",
    "not_after": "2021-11-19T05:00:15",
    "serial_number": "03abe9017d6de5eda90"
  },
  {
    "issuer_ca_id": 6864563267,
    "issuer_name": "C=US, O=Let's Encrypt, CN=R3",
    "common_name": "matomo.inlanefreight.com",
    "name_value": "matomo.inlanefreight.com",
    "id": 5081529377,
    "entry_timestamp": "2021-08-21T06:00:16.932",
    "not_before": "2021-08-21T05:00:16",
    "not_after": "2021-11-19T05:00:15",
    "serial_number": "03abe90104e271c98a90"
  },
  {
    "issuer_ca_id": 113123452,
    "issuer_name": "C=US, O=Let's Encrypt, CN=R3",
    "common_name": "smartfactory.inlanefreight.com",
    "name_value": "smartfactory.inlanefreight.com",
    "id": 4941235512141012357,
    "entry_timestamp": "2021-07-27T00:32:48.071",
    "not_before": "2021-07-26T23:32:47",
    "not_after": "2021-10-24T23:32:45",
    "serial_number": "044bac5fcc4d59329ecbbe9043dd9d5d0878"
  },
  { ... SNIP ...
```

If needed, we can also have them filtered by the unique subdomains.

```shell-session
R3ubenR4512@htb[/htb]$ curl -s https://crt.sh/\?q\=inlanefreight.com\&output\=json | jq . | grep name | cut -d":" -f2 | grep -v "CN=" | cut -d'"' -f2 | awk '{gsub(/\\n/,"\n");}1;' | sort -u

account.ttn.inlanefreight.com
blog.inlanefreight.com
bots.inlanefreight.com
console.ttn.inlanefreight.com
ct.inlanefreight.com
data.ttn.inlanefreight.com
*.inlanefreight.com
inlanefreight.com
integrations.ttn.inlanefreight.com
iot.inlanefreight.com
mails.inlanefreight.com
marina.inlanefreight.com
marina-live.inlanefreight.com
matomo.inlanefreight.com
next.inlanefreight.com
noc.ttn.inlanefreight.com
preview.inlanefreight.com
shop.inlanefreight.com
smartfactory.inlanefreight.com
ttn.inlanefreight.com
vx.inlanefreight.com
www.inlanefreight.com
```

##### Company Hosted Servers
```shell-sessionell-session
R3ubenR4512@htb[/htb]$ for i in $(cat subdomainlist);do host $i | grep "has address" | grep inlanefreight.com | cut -d" " -f1,4;done

blog.inlanefreight.com 10.129.24.93
inlanefreight.com 10.129.27.33
matomo.inlanefreight.com 10.129.127.22
www.inlanefreight.com 10.129.127.33
s3-website-us-west-2.amazonaws.com 10.129.95.250
```

### FTP
The File Transfer Protocol (FTP) is one of the oldest protocols on the Internet. The FTP runs within the application layer of the TCP/IP protocol stack.

#### TFTP
Trivial File Transfer Protocol (TFTP) is simpler than FTP and performs file transfers between client and server processes. However, it does not provide user authentication and other valuable features supported by FTP.

Let us take a look at a few commands of `TFTP`:

| Commands | Description                                                                                                                            |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| connect  | Sets the remote host, and optionally the port, for file transfers.                                                                     |
| get      | Transfers a file or set of files from the remote host to the local host.                                                               |
| put      | Transfers a file or set of files from the local host onto the remote host.                                                             |
| quit     | Exits tftp.                                                                                                                            |
| status   | Shows the current status of tftp, including the current transfer mode (ascii or binary), connection status, time-out value, and so on. |
| verbose  | Turns verbose mode, which displays additional information during file transfer, on or off.                                             |
Unlike the FTP client, `TFTP` does not have directory listing functionality.

##### Default Configuration
One of the most used FTP servers on Linux-based distributions is vsFTPd. The default configuration of vsFTPd can be found in /etc/vsftpd.conf, and some settings are already predefined by default.

###### vsFTPd Config File

```shell-session
R3ubenR4512@htb[/htb]$ cat /etc/vsftpd.conf | grep -v "#"
```

| **Setting**                                                   | **Description**                                                                                          |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `listen=NO`                                                   | Run from inetd or as a standalone daemon?                                                                |
| `listen_ipv6=YES`                                             | Listen on IPv6 ?                                                                                         |
| `anonymous_enable=NO`                                         | Enable Anonymous access?                                                                                 |
| `local_enable=YES`                                            | Allow local users to login?                                                                              |
| `dirmessage_enable=YES`                                       | Display active directory messages when users go into certain directories?                                |
| `use_localtime=YES`                                           | Use local time?                                                                                          |
| `xferlog_enable=YES`                                          | Activate logging of uploads/downloads?                                                                   |
| `connect_from_port_20=YES`                                    | Connect from port 20?                                                                                    |
| `secure_chroot_dir=/var/run/vsftpd/empty`                     | Name of an empty directory                                                                               |
| `pam_service_name=vsftpd`                                     | This string is the name of the PAM service vsftpd will use.                                              |
| `rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem`          | The last three options specify the location of the RSA certificate to use for SSL encrypted connections. |
| `rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key` |                                                                                                          |
| `ssl_enable=NO`                                               |                                                                                                          |
In addition, there is a file called /etc/ftpusers that we also need to pay attention to, as this file is used to deny certain users access to the FTP service.

##### FTPUSERS

```shell-session
R3ubenR4512@htb[/htb]$ cat /etc/ftpusers

guest
john
kevin
```

##### Dangerous Settings
There are many different security-related settings we can make on each FTP server. These can have various purposes, such as testing connections through the firewalls, testing routes, and authentication mechanisms.

| **Setting**                    | **Description**                                                                    |
| ------------------------------ | ---------------------------------------------------------------------------------- |
| `anonymous_enable=YES`         | Allowing anonymous login?                                                          |
| `anon_upload_enable=YES`       | Allowing anonymous to upload files?                                                |
| `anon_mkdir_write_enable=YES`  | Allowing anonymous to create new directories?                                      |
| `no_anon_password=YES`         | Do not ask anonymous for password?                                                 |
| `anon_root=/home/username/ftp` | Directory for anonymous.                                                           |
| `write_enable=YES`             | Allow the usage of FTP commands: STOR, DELE, RNFR, RNTO, MKD, RMD, APPE, and SITE? |
##### Anonymous Login

```shell-sessionell-session
R3ubenR4512@htb[/htb]$ ftp 10.129.14.136

Connected to 10.129.14.136.
220 "Welcome to the HTB Academy vsFTP service."
Name (10.129.14.136:cry0l1t3): anonymous

230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.


ftp> ls

200 PORT command successful. Consider using PASV.
150 Here comes the directory listing.
-rw-rw-r--    1 1002     1002      8138592 Sep 14 16:54 Calender.pptx
drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Clients
drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Documents
drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Employees
-rw-rw-r--    1 1002     1002           41 Sep 14 16:45 Important Notes.txt
226 Directory send OK.
```

##### Download a File
```shell-sessionell-session
ftp> ls

200 PORT command successful. Consider using PASV.
150 Here comes the directory listing.
-rwxrwxrwx    1 ftp      ftp             0 Sep 16 17:24 Calendar.pptx
drwxrwxrwx    4 ftp      ftp          4096 Sep 16 17:57 Clients
drwxrwxrwx    2 ftp      ftp          4096 Sep 16 18:05 Documents
drwxrwxrwx    2 ftp      ftp          4096 Sep 16 17:24 Employees
-rwxrwxrwx    1 ftp      ftp            41 Sep 18 15:58 Important Notes.txt
226 Directory send OK.


ftp> get Important\ Notes.txt

local: Important Notes.txt remote: Important Notes.txt
200 PORT command successful. Consider using PASV.
150 Opening BINARY mode data connection for Important Notes.txt (41 bytes).
226 Transfer complete.
41 bytes received in 0.00 secs (606.6525 kB/s)


ftp> exit

221 Goodbye.
```

##### Upload a File

```shell-session
R3ubenR4512@htb[/htb]$ touch testupload.txt
```

With the `PUT` command, we can upload files in the current folder to the FTP server.


```shell-session
ftp> put testupload.txt 

local: testupload.txt remote: testupload.txt
---> PORT 10,10,14,4,184,33
200 PORT command successful. Consider using PASV.
---> STOR testupload.txt
150 Ok to send data.
226 Transfer complete.


ftp> ls

---> TYPE A
200 Switching to ASCII mode.
---> PORT 10,10,14,4,223,101
200 PORT command successful. Consider using PASV.
---> LIST
150 Here comes the directory listing.
-rw-rw-r--    1 1002     1002      8138592 Sep 14 16:54 Calender.pptx
drwxrwxr-x    2 1002     1002         4096 Sep 14 17:03 Clients
drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Documents
drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Employees
-rw-rw-r--    1 1002     1002           41 Sep 14 16:45 Important Notes.txt
-rw-------    1 1002     133             0 Sep 15 14:57 testupload.txt
226 Directory send OK.
```