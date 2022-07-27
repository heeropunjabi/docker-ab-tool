## Ddocker-ab-tool

    a simple apache benchmark tool packed into docker having lot of configuration to test your system at scale.

## give a load to your API

    docker run --rm --sysctl net.ipv4.ip_local_port_range="15000 65000" ab -r -s 5 -k -v 3 -m GET -l -c 20000 -n 20000 <api-url>

    To test remove URL:

    For e.g:
    docker run --rm --sysctl net.ipv4.ip_local_port_range="15000 65000" ab -r -s 5 -k -v 3 -m GET -l -c 10 -n 10 https://www.amazon.com/

    # Note: If you want to test the API locally you can give the ip as http://192.168.65.2 instead of localhost [# reason please check this comment --> https://github.com/docker/for-mac/issues/2965#issuecomment-520557292]

    docker run --rm --sysctl net.ipv4.ip_local_port_range="15000 65000" ab -r -s 5 -k -v 3 -m GET -l -c 20000 -n 20000 http://192.168.65.2:9900/

### build from source

    docker build -t ab .

### Reference material

    https://medium.com/mercedes-benz-techinnovation-blog/tuning-network-sysctls-in-docker-and-kubernetes-766e05da4ff2
