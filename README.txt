                  Private rhs-hadoop-deploy repo files

build-deploy-rhs-ambari-installer.sh:
------------------------------------
This script git pulls the latest glusterfs-hadoop-install and rhs-hadoop-install
repos, executes mk_tarball.sh to convert an Ambari .odt document to pdf and
create a tarball, and then pushes that tarball to s3. It is used by Red Hat to
make version of the rhs-hadoop-install package to SAs, customers, partners, etc.


mk_tarball:
----------
Use --help to see script command line options.

This script converts the .odt file (if present) to a PDF and then creates a
tarball containing the minimal set of files necessary for RHS-Ambari installs.

The script is expected to be run in the same dir where a git pull or git clone
is done.

Note: there is a depdendency on libreoffice. To install it:
 wget http://download.documentfoundation.org/libreoffice/stable/4.1.0/rpm/x86_64/LibreOffice_4.1.0_Linux_x86-64_rpm.tar.gz
 tar -xvf Libre*gz
 cd Libre*
 cd RPMS/
 yum install -y *rpm

Then create a symlink to the downloaded version, eg:
 ln -s /usr/bin/libreoffice4.1 /bin/libreoffice


shelltest.sh:
-----------
Not used.
