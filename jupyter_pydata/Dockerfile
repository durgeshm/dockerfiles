FROM ubuntu:16.04
MAINTAINER "Durgesh Mankekar"

RUN apt-get update && apt-get install -y wget bzip2 ca-certificates git curl vim python3-dev python3-pip

RUN pip3 install --upgrade pip
RUN pip3 install numpy scipy pandas matplotlib seaborn jupyter

RUN ["mkdir", "notebooks"]
COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /

CMD ["/run_jupyter.sh"]

