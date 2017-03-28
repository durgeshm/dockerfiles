FROM ubuntu:16.04
MAINTAINER "Durgesh Mankekar"

RUN apt-get update && apt-get install -y wget bzip2 ca-certificates \
    git curl vim python3-dev python3-pip \
    libfreetype6-dev libpng12-dev

RUN pip3 install --upgrade pip
RUN pip3 install numpy pandas matplotlib seaborn Pillow jupyter

RUN ["mkdir", "notebooks"]
COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /

VOLUME /notebooks

CMD ["/run_jupyter.sh"]

