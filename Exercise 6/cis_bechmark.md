# SOME CIS BENCHMARK IMPLENTATION ON UBUNTU 
1. ***Ensure minimum days between password changes is configured.***
To prevent user from circumventing the password reuse control, the minimum numbers of days before a change of password is set to 1 or greater. This configuration is carried out in the etc/login.defs file by assigning PASS_MIN_DAYS a greater than 0.

```sh
    # PASS_MIN_DAYS
```
2. ***Ensure root login is restricted to system console.***
The file `/etc/securetty` contains a list of valid terminals that may be logged in directly as 
root. All entries for any consoles that are not in a physically secure location should be removed.

1. ***Ensure permissions on /etc/passwd are configured.***
It is important to ensure that the `/etc/passwd` file is protected from unauthorized write 
access. Run the following command and verify `Uid` and `Gid` are both 0/root and Access is 644:
```sh
    # stat /etc/passwd
```
Run the following command to set permissions on /etc/passwd:
```sh
    # chown root:root /etc/passwd
    # chmod u-x,go-wx /etc/passwd
```

4. ***Ensure permissions on /etc/gshadow- are configured.***
The /etc/gshadow- file is used to store backup information about groups that is critical to 
the security of those accounts, It is critical to ensure that the /etc/gshadow- file is protected from unauthorized access. Run the following command and verify Uid is 0/root, Gid is 0/root or <gid>/shadow, and access is 640 or more restrictive
```sh
    # stat /etc/gshadow-
```
 Run one of the following commands to set ownership of /etc/gshadow- to root and group 
to either root or shadow:
```sh
    # chown root:root /etc/gshadow-
    # chown root:shadow /etc/gshadow-
```
Run the following command to remove excess permissions form /etc/gshadow-:
```sh
    # chmod u-x,g-wx,o-rwx /etc/gshadow-
```
