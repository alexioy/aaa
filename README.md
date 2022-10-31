#DockerFile for Nokia Debug Pod Jira FNCOIMAINT-99
#V1.0
FROM debian
LABEL maintainer="Antony Alexiou"

COPY . /Nokia-net-Tools
WORKDIR /Nokia-net-Tools
RUN apt-get update
RUN  apt-get install apt-utils
RUN  apt-get install -y  iftop iptraf  iputils-ping tcpdump hping3 nmap net-tools
RUN echo " This is a Debug Pod and will close on exit. Do not save any data on this pod.Use kubectl copy from the HOST instead."
CMD ["echo", " This is a Debug Pod and will close on exit. Do not save any data on this pod.Use kubectl copy from the HOST instead."]
