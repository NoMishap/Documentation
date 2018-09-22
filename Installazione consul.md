```bash
git clone https://github.com/NoMishap/Consul.git
curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-6.3.2-amd64.deb
sudo dpkg -i metricbeat-6.3.2-amd64.deb
wget https://releases.hashicorp.com/consul/1.2.1/consul_1.2.1_linux_amd64.zip
sudo apt install unzip
unzip consul_1.2.1_linux_amd64.zip 
sudo cp Consul/metricbeat/config/metricbeat.yml /etc/metricbeat/
edit  /etc/metricbeat/metricbeat.yml with correct ip port
sudo systemctl enable metricbeat.service 
sudo systemctl start metricbeat.service 

 rm consul_* metricbeat-*
./consul agent -config-dir=./Consul/
./consul agent -config-dir=./Consul/ -ui -client 0.0.0.0
```

 

Hosts:

imolab 192.168.210.72 consul1

imolab 192.168.210.73 consul2

garr 90.147.189.74 consul4



Ip port on pfsense

88.147.126.145 8012 Consul wan gossip

88.147.126.145 8013 elasticsearch



create a vpn across datacenter

port 8014 

ip 88.147.126.145



[consul multidatacenter with NAT](http://www.devtech101.com/2017/08/31/using-consul-service-discovery-multiple-data-centers-part-1/)