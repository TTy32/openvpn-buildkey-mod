openvpn-buildkey-mod
--------------------

= Description

This bash script is meant to be used as a replacement for build-key in the easy-rsa directory of openvpn.

This script will create a directory with a name you specify. Inside of it, it will create an openvpn and tunnelblick folder.

It then copies the ca.crt, .key and .crt file to the openvpn directory and tunnelblickdirectory in keys/<name>/tunnelblick/<name>-<openvpn config>.tblk/Contents/Resources

At last the openvpn config files in a template directory are copied in keys/<name>/openvpn and the appropiate .tblk directory's.

For cleanup the client.* keys in keys/ are deleted.

You will end up with a directory with openvpn configs and tunnelblick packages ready to be copied and used to tunnelblick and/or openvpn installation in linux/windows.

= Installation

Install p7zip-full for 7z to work.

Copy the script in /etc/openvpn/easy-rsa/keys

Copy your template configs in the ./templates folder. Make sure you use the filename client.<extension> in the configs, as the key files will have this name.

Adjust the password in the script, default "password" is used. Notice the preceding but adjecent "-p". This just 7z syntax.

= Usage

Do the usual . vars first. Then execute the build-key-mod script, it takes one command-line argument. This argument will be the name for the directory stored in keys/ and the prefix for the .ovpn files and .tblk directory's

Enter all the credentials as you normally would.

Et voila, your directory is ready in keys/ and a nice and small password-protected 7z file is alse created.
