
CentOSでサードパーティリポジトリを追加
rpm -Uvh https://download.postgresql.org/pub/repos/yum/9.4/redhat/rhel-6-x86_64/pgdg-centos94-9.4-3.noarch.rpm

yum localinstall pgdg-centos94-9.4-1.noarch.rpm


CentOSにpostgresを入れる場合の注意点。
postgrses→httpd→phpの順にインストールしないと、pg_connnect() がUndefinedに
なる場合がある。

yum -y install postgresql94.x86_64 postgresql94-contrib.x86_64 postgresql94-devel.x86_64 postgresql94-server.x86_64 postgresql94-libs

//php56 をpostgresライブラリと一緒にインストールする。
yum --enablerepo=remi,epel,rpmforge,remi-php56 -y install php php-devel php-mbstring php-mcrypt  php-fpm php-pear php-opcache php-gd php-pgsql


