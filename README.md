# git-test
mkdir /home/key
cd /home/key
openssl genrsa -out dashboard.key 2048
openssl req -new -sha256 -out dashboard.csr -key dashboard.key -subj '/CN=192.168.201.1'
openssl x509 -req -sha256 -days 3650 -in dashboard.csr -signkey dashboard.key -out dashboard.crt
cat dashboard.crt | base64
cat dashboard.key | base64
