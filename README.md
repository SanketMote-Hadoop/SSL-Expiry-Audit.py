# SSL-Expiry-Audit.py
SSL Expiry audit script
yum install python-pip python-setuptools    //To install parallel-ssh, you need to first install PIP on your Linux system.
sudo pip install parallel-ssh   //Then install parallel-ssh using pip as follows
vim hosts  //add all host where you want to run this script{192.168.0.10:22 192.168.0.11:22 192.168.0.12:22}
//parallel-ssh -h hosts "uptime; df -h" you can run such commands on all server which are added in host file.
//Now run parallel-ssh, specify the hosts file using the -h option and a command(s) that will be executed on all the specified servers. The -i flag means display std output and std error as execution of the command on each server completes.
parallel-ssh -h hosts "echo |openssl s_client -connect ${server}.hosts 2>/dev/null |openssl x509 -noout -subject -dates"
