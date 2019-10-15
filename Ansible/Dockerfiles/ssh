FROM local:base
RUN apt-get install -y task-ssh-server; /etc/init.d/ssh start


CMD /usr/sbin/sshd -D -o PermitRootLogin=Yes && tail -f /dev/null
