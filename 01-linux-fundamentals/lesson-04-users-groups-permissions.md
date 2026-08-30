# Lesson 4 - Linux Users, Groups and File Permissions

## Users and Groups

Commands learned:

- whoami - shows the current user
- id - shows user ID, group ID and group membership
- groups - shows the groups a user belongs to
- sudo -l - shows the commands a user is allowed to run with sudo

## File Permissions

Linux uses three basic permissions:

- r - read
- w - write
- x - execute

Permissions are assigned to:

- Owner
- Group
- Others

Example:

-rw-r-----

This means:

- Owner - read and write
- Group - read only
- Others - no access

## Numeric Permissions

Permission values:

- r = 4
- w = 2
- x = 1

Examples:

- 600 = rw-------
- 640 = rw-r-----
- 644 = rw-r--r--
- 755 = rwxr-xr-x
- 540 = r-xr-----

## chmod

chmod is used to change file permissions.

Examples:

- chmod 600 secret.txt
- chmod 640 incident-report.txt
- chmod g+r secret.txt
- chmod g-r secret.txt
- chmod u+x secret.txt
- chmod u-x secret.txt
- chmod a+r secret.txt
- chmod u=rw,g=r,o= secret.txt

Symbolic permissions:

- u = owner
- g = group
- o = others
- a = all
- + = add
- - = remove
- = = set exactly

## File Ownership

Commands learned:

- chown - changes file ownership
- chgrp - changes group ownership

Examples:

- sudo chgrp users secret.txt
- sudo chown michael:adm secret.txt

## Practical Exercise

Created:

incident-report.txt

Final configuration:

- Owner: michael
- Group: adm
- Owner permissions: read and write
- Group permissions: read
- Others: no access

Final permission:

-rw-r-----

Numeric permission:

640

## Cybersecurity Connection

Linux permissions and ownership are important for access control and the principle of least privilege.

They help ensure that users only have the permissions they need to access or modify files and resources.
