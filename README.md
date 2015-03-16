git2rpm
=======

Requirements
------------

+ bash (http://www.gnu.org/software/bash/)
+ rpm-build

Installation
------------

```
$ git clone https://github.com/hansode/git2rpm.git
```

Usage
-----

```
$ git2rpm <git repository uri>
```

Getting Started
---------------

```
$ ./git2rpm https://github.com/hansode/makistrano.git
+ repouri=https://github.com/hansode/makistrano.git
+ reponame=makistrano.git
+ reponame=makistrano
+ reponame=rpm4makistrano
+ mkdir -p /home/vagrant/rpmbuild/BUILD /home/vagrant/rpmbuild/BUILDROOT /home/vagrant/rpmbuild/RPMS /home/vagrant/rpmbuild/SOURCES /home/vagrant/rpmbuild/SPECS /home/vagrant/rpmbuild/SRPMS
+ [[ -d rpm4makistrano ]]
+ cd rpm4makistrano
+ git pull
Already up-to-date.
++ git log HEAD -n 1 --pretty=format:%h
+ git_version=2add2a4
+++ git log 2add2a4 -n 1 --pretty=format:%cd --date=iso
++ date '--date=2013-11-18 18:07:42 -0800' +%Y%m%d%H%M%S
+ git_datetime=20131119110742
+ build_id=20131119110742git2add2a4
+ cd /home/vagrant/rpmbuild/SPECS
+ cat
+ rpmbuild -bb rpm4makistrano.spec --define 'repouri https://github.com/hansode/makistrano.git' --define 'reponame rpm4makistrano' --define 'build_id 20131119110742git2add2a4'
Executing(%prep): /bin/sh -e /var/tmp/rpm-tmp.qpo4o6
+ umask 022
+ cd /home/vagrant/rpmbuild/BUILD
+ LANG=C
+ export LANG
+ unset DISPLAY
+ '[' -d rpm4makistrano-20131119110742git2add2a4 ']'
+ rm -rf rpm4makistrano-20131119110742git2add2a4
+ git clone https://github.com/hansode/makistrano.git rpm4makistrano-20131119110742git2add2a4
Initialized empty Git repository in /home/vagrant/rpmbuild/BUILD/rpm4makistrano-20131119110742git2add2a4/.git/
remote: Counting objects: 278, done.
remote: Total 278 (delta 0), reused 0 (delta 0), pack-reused 278
Receiving objects: 100% (278/278), 36.30 KiB, done.
Resolving deltas: 100% (106/106), done.
+ cd rpm4makistrano-20131119110742git2add2a4
+ :
+ cd /home/vagrant/rpmbuild/BUILD
+ cd rpm4makistrano-20131119110742git2add2a4
+ /bin/chmod -Rf a+rX,u+w,g-w,o-w .
+ exit 0
Executing(%build): /bin/sh -e /var/tmp/rpm-tmp.pRFBqi
+ umask 022
+ cd /home/vagrant/rpmbuild/BUILD
+ cd rpm4makistrano-20131119110742git2add2a4
+ LANG=C
+ export LANG
+ unset DISPLAY
+ exit 0
Executing(%install): /bin/sh -e /var/tmp/rpm-tmp.bbDnBu
+ umask 022
+ cd /home/vagrant/rpmbuild/BUILD
+ '[' /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64 '!=' / ']'
+ rm -rf /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
++ dirname /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
+ mkdir -p /home/vagrant/rpmbuild/BUILDROOT
+ mkdir /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
+ cd rpm4makistrano-20131119110742git2add2a4
+ LANG=C
+ export LANG
+ unset DISPLAY
+ rm -rf /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
+ mkdir -p /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64//home/git2rpm/rpm4makistrano
++ pwd
+ rsync -aHA --exclude=.git '--exclude=.git/*' /home/vagrant/rpmbuild/BUILD/rpm4makistrano-20131119110742git2add2a4/ /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64//home/git2rpm/rpm4makistrano/
+ /usr/lib/rpm/find-debuginfo.sh --strict-build-id /home/vagrant/rpmbuild/BUILD/rpm4makistrano-20131119110742git2add2a4
+ /usr/lib/rpm/check-rpaths /usr/lib/rpm/check-buildroot
+ /usr/lib/rpm/redhat/brp-compress
+ /usr/lib/rpm/redhat/brp-strip-static-archive /usr/bin/strip
+ /usr/lib/rpm/redhat/brp-strip-comment-note /usr/bin/strip /usr/bin/objdump
+ /usr/lib/rpm/brp-python-bytecompile
+ /usr/lib/rpm/redhat/brp-python-hardlink
+ /usr/lib/rpm/redhat/brp-java-repack-jars
Processing files: rpm4makistrano-20131119110742git2add2a4-1.el6.noarch
Requires(rpmlib): rpmlib(CompressedFileNames) <= 3.0.4-1 rpmlib(FileDigests) <= 4.6.0-1 rpmlib(PayloadFilesHavePrefix) <= 4.0-1
Requires: /bin/bash /bin/sh
Checking for unpackaged file(s): /usr/lib/rpm/check-files /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
warning: Could not canonicalize hostname: vagrant-centos6
Wrote: /home/vagrant/rpmbuild/RPMS/noarch/rpm4makistrano-20131119110742git2add2a4-1.el6.noarch.rpm
Executing(%clean): /bin/sh -e /var/tmp/rpm-tmp.xqZHo1
+ umask 022
+ cd /home/vagrant/rpmbuild/BUILD
+ cd rpm4makistrano-20131119110742git2add2a4
+ rm -rf /home/vagrant/rpmbuild/BUILDROOT/rpm4makistrano-20131119110742git2add2a4-1.el6.x86_64
+ exit 0
```

```
$ sudo yum install --disablerepo='*' /home/vagrant/rpmbuild/RPMS/noarch/rpm4makistrano-20131119110742git2add2a4-1.el6.noarch.rpm                  Loaded plugins: fastestmirror
Setting up Install Process
Examining /home/vagrant/rpmbuild/RPMS/noarch/rpm4makistrano-20131119110742git2add2a4-1.el6.noarch.rpm: rpm4makistrano-20131119110742git2add2a4-1.el6.noarch
Marking /home/vagrant/rpmbuild/RPMS/noarch/rpm4makistrano-20131119110742git2add2a4-1.el6.noarch.rpm to be installed
Loading mirror speeds from cached hostfile
Resolving Dependencies
--> Running transaction check
---> Package rpm4makistrano.noarch 0:20131119110742git2add2a4-1.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===================================================================================================================================================================================
 Package                        Arch                   Version                                         Repository                                                             Size
===================================================================================================================================================================================
Installing:
 rpm4makistrano                 noarch                 20131119110742git2add2a4-1.el6                  /rpm4makistrano-20131119110742git2add2a4-1.el6.noarch                  40 k

Transaction Summary
===================================================================================================================================================================================
Install       1 Package(s)

Total size: 40 k
Installed size: 40 k
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : rpm4makistrano-20131119110742git2add2a4-1.el6.noarch                                                                                                            1/1
  Verifying  : rpm4makistrano-20131119110742git2add2a4-1.el6.noarch                                                                                                            1/1

Installed:
  rpm4makistrano.noarch 0:20131119110742git2add2a4-1.el6

Complete!
```

```
$ rpm -qi rpm4makistrano
Name        : rpm4makistrano               Relocations: /home/git2rpm/rpm4makistrano
Version     : 20131119110742git2add2a4          Vendor: (none)
Release     : 1.el6                         Build Date: Mon 16 Mar 2015 06:31:31 PM JST
Install Date: Mon 16 Mar 2015 06:33:05 PM JST      Build Host: vagrant-centos6
Group       : Unspecified                   Source RPM: rpm4makistrano-20131119110742git2add2a4-1.el6.src.rpm
Size        : 41404                            License: BSD
Signature   : (none)
URL         : https://github.com/hansode/makistrano.git
Summary     : git2rpm
Description :

```

```
$ rpm -ql rpm4makistrano
/home/git2rpm/rpm4makistrano
/home/git2rpm/rpm4makistrano/.travis.yml
/home/git2rpm/rpm4makistrano/Makefile
/home/git2rpm/rpm4makistrano/README.md
/home/git2rpm/rpm4makistrano/bin
/home/git2rpm/rpm4makistrano/bin/maki
/home/git2rpm/rpm4makistrano/examples
/home/git2rpm/rpm4makistrano/examples/Makifile
/home/git2rpm/rpm4makistrano/functions
/home/git2rpm/rpm4makistrano/functions/makistrano.sh
/home/git2rpm/rpm4makistrano/test
/home/git2rpm/rpm4makistrano/test/Makefile
/home/git2rpm/rpm4makistrano/test/integration
/home/git2rpm/rpm4makistrano/test/integration/Makefile
/home/git2rpm/rpm4makistrano/test/integration/makistrano
/home/git2rpm/rpm4makistrano/test/integration/makistrano/Makefile
/home/git2rpm/rpm4makistrano/test/integration/makistrano/helper_shunit2.sh
/home/git2rpm/rpm4makistrano/test/integration/makistrano/t.makistrano_cli.sh
/home/git2rpm/rpm4makistrano/test/shunit2
/home/git2rpm/rpm4makistrano/test/unit
/home/git2rpm/rpm4makistrano/test/unit/Makefile
/home/git2rpm/rpm4makistrano/test/unit/makistrano
/home/git2rpm/rpm4makistrano/test/unit/makistrano/Makefile
/home/git2rpm/rpm4makistrano/test/unit/makistrano/helper_shunit2.sh
/home/git2rpm/rpm4makistrano/test/unit/makistrano/t.makistrano_cli.sh
/home/git2rpm/rpm4makistrano/test/unit/makistrano/t.makistrano_eval.sh
/home/git2rpm/rpm4makistrano/test/unit/makistrano/t.makistrano_load_config.sh
/home/git2rpm/rpm4makistrano/test/unit/makistrano/t.makistrano_node.sh
/home/git2rpm/rpm4makistrano/test/unit/makistrano/t.makistrano_nodes.sh
```
