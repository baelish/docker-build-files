Start the container:

    docker run -d --name=dhcpd --volume='type=bind,src=<path to>/example-data,dst=/data' baelish/dhcpd
