Create network config to create Vlan interface.

    echo "Description='Virtual LAN 11 on interface enp2s0'
    Interface=enp2s0.11
    Connection=vlan
    BindsToInterfaces=enp2s0
    VLANID=11
    IP=static
    " > /etc/netctl/enp2s0-vlan11

Enable and start network interface.

    netctl enable enp2s0-vlan11
    netctl start enp2s0-vlan11

Create the docker network.

    docker network create -d macvlan --subnet 10.66.11.0/24 --gateway=10.66.11.254 -o parent=enp2s0.11 server-net

Start the container with specific network requirements.

    docker run -d --net=server-net --ip=10.66.11.1 --name=caching-dns --volume=/var/lib/docker/volumes/caching-dns:/data baelish/caching-dns
