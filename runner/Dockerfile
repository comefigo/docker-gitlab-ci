FROM gitlab/gitlab-runner:latest

# add sudo user
RUN echo '%gitlab-runner ALL=(ALL) NOPASSWD: ALL\n' > /etc/sudoers.d/gitlab-runner

# update libs
RUN sudo apt-get update \
    && sudo apt-get -y upgrade

# install python libs
RUN sudo apt-get install -y python3 build-essential python-dev

# install pip
RUN curl -kL "https://bootstrap.pypa.io/get-pip.py" | python

# install aws cli
RUN pip install awscli
