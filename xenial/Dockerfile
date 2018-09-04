# PyEnv on Ubuntu 16.04 (Xenial)
# VERSION               0.1

FROM ubuntu:16.04
MAINTAINER John Vrbanac <john.vrbanac@linux.com>

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update && \
    apt-get -y install \
        git make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev \
        libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils \
        libffi-dev liblzma-dev


RUN git clone git://github.com/yyuu/pyenv.git .pyenv
RUN git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv

ENV HOME  /
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH

RUN pyenv install 2.7.15
RUN pyenv install 3.7.0
RUN pyenv install 3.4.8
RUN pyenv install 3.5.5
RUN pyenv install 3.6.6
RUN pyenv install pypy2.7-6.0.0
RUN pyenv install pypy3.5-6.0.0

RUN pyenv global 2.7.15 3.7.0 3.6.6 3.5.5 3.4.8 pypy3.5-6.0.0 pypy2.7-6.0.0
RUN pip install -U pip tox
