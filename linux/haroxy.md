yum install -y haproxy
systemctl enable haproxy.service
service haproxy start

vi /etc/haproxy/haproxy.cfg

frontend stapp-fr
   bind 0.0.0.0:80/ *:80
   default_backend   stapp-backend

backend stapp-backend
   balance  roundrobin
   server stapp01 stapp01:80 check
   server stapp02 stapp02:80 check
   server stapp03 stapp03:80 check