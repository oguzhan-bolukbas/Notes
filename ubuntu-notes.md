## Fix apt-get update “the following signatures couldn’t be verified because the public key is not available”

Error example:

[chris@server ~]$ sudo apt-get update
Ign http://security.ubuntu.com trusty-security InRelease
Get:1 http://security.ubuntu.com trusty-security Release.gpg [933 B]
...
Fetched 21.9 MB in 14s (1,537 kB/s)
Reading package lists... Done
W: GPG error: http://security.ubuntu.com trusty-security Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 40976EAF437D05B5 NO_PUBKEY 3B4FE6ACC0B21F32
W: GPG error: http://archive.canonical.com trusty Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 40976EAF437D05B5 NO_PUBKEY 3B4FE6ACC0B21F32
W: GPG error: http://archive.ubuntu.com trusty Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 40976EAF437D05B5 NO_PUBKEY 3B4FE6ACC0B21F32
W: GPG error: http://archive.ubuntu.com trusty-updates Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 40976EAF437D05B5 NO_PUBKEY 3B4FE6ACC0B21F32



If these errors aren’t fixed, apt will have problems when installing or upgrading packages. For example:

[chris@server ~]$ sudo apt-get upgrade
Reading package lists... Done
Building dependency tree... Done
Calculating upgrade... Done
...
E: Some packages could not be authenticated



To add these keys, run the following commands: (Key'ler ayrı ayrı eklenmeli)

[chris@server ~]$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 40976EAF437D05B5

-------------------------------------------------------------------------------



## Helm installation:

From Apt (Debian/Ubuntu)

Members of the Helm community have contributed a Helm package for Apt. This package is generally up to date.

`curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -`
`sudo apt-get install apt-transport-https --yes`
`echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list`
`sudo apt-get update`
`sudo apt-get install helm`

-------------------------------------------------------------------------------




