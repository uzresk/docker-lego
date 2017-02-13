FROM uzresk/ansible-serverspec:latest

LABEL maintainer "uzresk"

# set locale ja_JP.UTF-8, timezone
RUN localedef -v -c -i ja_JP -f UTF-8 ja_JP.UTF-8; echo "";
ENV LANG=ja_JP.UTF-8
RUN rm -f /etc/localtime
RUN ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# install jupyter and jupyter extension
RUN pip install jupyter
RUN pip install jupyter_nbextensions_configurator && \
    pip install https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tarball/master && \
    jupyter contrib nbextension install --user && \
    jupyter nbextension enable toc2/main && \
    pip install jupyterthemes

# install uses lego
RUN yum -y install iproute \
                   unzip \
                   java-1.8.0-openjdk.x86_64 \
                   java-1.8.0-openjdk-devel.x86_64

