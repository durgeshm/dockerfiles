FROM nvidia/cuda:8.0-cudnn5-devel-ubuntu16.04
MAINTAINER "Durgesh Mankekar"

RUN apt-get update && apt-get install -y wget ca-certificates \
    git curl vim python3-dev python3-pip \
    libfreetype6-dev libpng12-dev

RUN pip3 install --upgrade pip
RUN pip3 install numpy pandas sklearn matplotlib seaborn jupyter
RUN pip3 install http://download.pytorch.org/whl/cu80/torch-0.1.10.post2-cp35-cp35m-linux_x86_64.whl 
RUN pip3 install torchvision

RUN ["mkdir", "notebooks"]
COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /

# Jupyter port
EXPOSE 8888

# Store notebooks in this mounted directory
VOLUME /notebooks

CMD ["/run_jupyter.sh"]

