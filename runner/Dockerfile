FROM gitlab/gitlab-runner:latest

# update libs
RUN apt-get update \
    && apt-get -y upgrade \
    && apt-get install sudo

# add sudo user
RUN echo '%gitlab-runner ALL=(ALL) NOPASSWD: ALL\n' > /etc/sudoers.d/gitlab-runner

# install python libs
RUN apt-get install -y python3 build-essential python-dev docker.io

# install pip
RUN curl -kL "https://bootstrap.pypa.io/get-pip.py" | python

# install aws cli
RUN pip install awscli ansible boto boto3 docker-py