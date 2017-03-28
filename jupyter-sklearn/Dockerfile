FROM ubuntu:16.04
MAINTAINER "Durgesh Mankekar"

RUN apt-get update && apt-get install -y wget bzip2 ca-certificates \
    git curl vim python3-dev python3-pip \
    libfreetype6-dev libpng12-dev

RUN pip3 install --upgrade pip
RUN pip3 install scikit-learn pandas matplotlib seaborn Pillow jupyter

RUN ["mkdir", "notebooks"]
COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /

# Jupyter port
EXPOSE 8888

# Store notebooks in this mounted directory
VOLUME /notebooks

CMD ["/run_jupyter.sh"]

