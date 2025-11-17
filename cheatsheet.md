-------------------------
Task1 — Quick Cheat-Sheet
-------------------------

Linux Basics
------------
pwd               # show current directory
ls -la            # list files with details and hidden files
cd /path          # change directory
mkdir lab1        # create directory
touch file.txt    # create empty file

File Permissions
----------------
ls -l             # list files with permissions & owner
chmod 755 file    # set permissions (rwxr-xr-x)
chown user:group file  # change file owner

Networking
----------
ip a              # show interfaces and IPs
ping 192.168.56.101  # test connectivity
netstat -tulpn    # list listening ports and processes
traceroute google.com  # trace network path

Nmap (scanning)
---------------
nmap -sS -p- <target>   # TCP SYN scan (all ports)
nmap -sV -O <target>    # service/version + OS detection
nmap -A <target>        # aggressive scan (scripts, OS, version)

OpenSSL (crypto)
----------------
openssl version
# AES symmetric encrypt
openssl enc -aes-256-cbc -pbkdf2 -salt -in plain.txt -out encrypted.bin
# AES decrypt
openssl enc -d -aes-256-cbc -pbkdf2 -in encrypted.bin -out decrypted.txt

# RSA key generation
openssl genpkey -algorithm RSA -out private.pem -pkeyopt rsa_keygen_bits:2048
openssl rsa -pubout -in private.pem -out public.pem
# RSA encrypt/decrypt
openssl pkeyutl -encrypt -pubin -inkey public.pem -in rsa_plain.txt -out rsa_encrypted.bin
openssl pkeyutl -decrypt -inkey private.pem -in rsa_encrypted.bin -out rsa_decrypted.txt

Hashing
-------
openssl dgst -md5 file.txt
openssl dgst -sha256 file.txt

Useful apt commands
-------------------
sudo apt update
sudo apt upgrade
sudo apt install <package-name>

Git (upload)
------------
git init
git add .
git commit -m "Task1: lab notes and cheat sheet"
git branch -M main
git remote add origin https://github.com/yourusername/repo.git
git push -u origin main
