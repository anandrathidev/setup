# setup
sudo yum install centos-release-scl
sudo yum install rh-python36
scl enable rh-python36 bash
sudo yum groupinstall 'Development Tools'


yum install https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm
yum install postgresql11
yum install postgresql11-server
yum install postgresql11-devel


/usr/pgsql-11/bin/postgresql-11-setup initdb
systemctl enable postgresql-11
systemctl start postgresql-11

sudo apt-get install libpq-dev

CREATE DATABASE  sxforum;
CREATE USER sxuser WITH PASSWORD 'hotcopper1';
ALTER ROLE sxuser SET client_encoding TO 'utf8';
ALTER ROLE sxuser SET default_transaction_isolation TO 'read committed';
ALTER ROLE sxuser SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE sxforum TO sxuser;

sudo groupadd dev

usermod -g groupname username
usermod -g dev dev1

chgrp dev /tmp
chmod g+rwx /tmp
 
 
 
CREATE DATABASE  realestate;
CREATE USER reuser WITH PASSWORD 'realestate1';
ALTER ROLE reuser SET client_encoding TO 'utf8';
ALTER ROLE reuser SET default_transaction_isolation TO 'read committed';
ALTER ROLE reuser SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE realestate TO reuser;

useradd dev2
usermod -g dev dev2


 
.bashrc 
# User specific aliases and functions
export PATH=$PATH:/usr/pgsql-11/bin/
source /opt/rh/rh-python36/enable
source ~/pydev/hc//bin/activate
cd ~/
 
