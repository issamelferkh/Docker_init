FROM ubuntu:latest
RUN apt-get update  && apt-get upgrade -y &&\
	DEBIAN_FRONTEND=noninteractive apt-get install apt-utils apt-transport-https curl openssh-server ca-certificates postfix -y && \
	DEBIAN_FRONTEND=noninteractive curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash && \
	DEBIAN_FRONTEND=noninteractive apt-get install -y gitlab-ce && \
	DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

WORKDIR /etc/gitlab
RUN sed -i '13s/http:\/\/gitlab.example.com/https:\/\/192.168.99.100/' gitlab.rb && \
	echo "nginx['enable'] = true" >> gitlab.rb && \
	echo "nginx['redirect_http_to_https'] = true" >> gitlab.rb && \
	echo "nginx['redirect_http_to_https_port'] = 80" >> gitlab.rb && \
	echo "nginx['ssl_certificate'] = '/etc/gitlab/ssl/gitlab.crt'" >> gitlab.rb && \
	echo "nginx['ssl_certificate_key'] = '/etc/gitlab/ssl/gitlab.key'" >> gitlab.rb && \
	echo "gitlab_rails['gitlab_shell_ssh_port'] = 2222" >> gitlab.rb && \
	echo "Port 2222" >> /etc/ssh/sshd_config

WORKDIR /
RUN echo "/opt/gitlab/embedded/bin/runsvdir-start& gitlab-ctl reconfigure" > start.sh && \
	echo "service ssh restart" >> start.sh && \
	echo "echo 'Done!'" >> start.sh && \
	echo "tail -f /dev/null" >> start.sh && \
	chmod 777 start.sh

EXPOSE 80 443 2222
CMD ["sh", "start.sh"]

# To build it?
# docker build -t ex03 .

# To run it?
# docker run -it --rm --privileged -p 80:80 -p 443:443 -p 2222:2222 ex03

# Clone HTTPS
# env GIT_SSL_NO_VERIFY=true git clone https://(docker-machine ip Char):443/<repo>.git

# Push HTTPS
# env GIT_SSL_NO_VERIFY=true git push

# Clone SSH
# ssh-keygen 
# git clone ssh://git@192.168.99.100:2222/root/test.git