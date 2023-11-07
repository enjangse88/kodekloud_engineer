firewall-cmd --permanent --zone=public --add-service=http 
firewall-cmd --permanent --zone=public --add-service={http,https,ftp}
firewall-cmd --permanent --zone=public --add-port=8080/tcp

firewall-cmd --permanent --zone=public --remove-service=http

firewall-cmd --permanent --zone=public --remove-service={http,https,ftp}

firewall-cmd --permanent --zone=public --remove-port=8080/tcp

firewall-cmd --list-all 
firewall-cmd --reload
