Linux Commands
=======================

https://www.linode.com/docs/tools-reference/linux-users-and-groups/

### Find out what linux version
```
$ cat /etc/redhat-release
> Red Hat Enterprise Linux Server release 7.2 (Maipo)
```

### Install PHP 7 on CentOS / RHEL 6.8 and 7.3 via Yum
source:
https://webtatic.com/packages/php70/

https://webtatic.com/packages/php71/


First we need to add Webtatic EL yum repository information to our corresponding
CentOS/RHEL version to Yum..
```
$ rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
```

After adding the new repo information we can use Yum to install PHP 7.

```
$ yum install php70w php70w-opcache
```
Alternatively you can install PHP 7.0's php-fpm SAPI
```
$ yum install php70w-fpm php70w-opcache
```

##### It is possible to upgrade PHP by
```
$ yum install yum-plugin-replace
$ yum replace php-common --replace-with=php70w-common
```

### Yum commands
List installed packages
```
$ yum list installed
```

### User commands
#### List
```
# Lists all users
$ cut -d: -f1 /etc/passwd
```

#### Add
```
# Create new user
$ useradd <username>

# Create new user with group
$ useradd -g <group> <username>
```

#### Remove
```
# Remove all groups from a user
$ usermod -G "" <name>

# Remove user
$ userdel <name>

# Remove user and their home folder and their files
$ userdel -r <name>
```

#### Switch
```
$ su - <username>
```
