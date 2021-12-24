FROM jupyter/scipy-notebook:latest

USER jovyan

WORKDIR /tmp

# Install dependencies
COPY ./requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Docker options
ENV JUPYTER_ENABLE_LAB=yes
ENV GRANT_SUDO=yes


WORKDIR /home/jovyan