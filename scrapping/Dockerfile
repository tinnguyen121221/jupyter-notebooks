FROM jupyter/scipy-notebook:latest

USER root
WORKDIR /tmp

RUN apt-get update \
    && apt-get install -y gnupg curl fonts-ipafont fonts-ipaexfont

RUN wget https://dl.google.com/linux/linux_signing_key.pub \
    && apt-key add linux_signing_key.pub \
    && echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | tee /etc/apt/sources.list.d/google-chrome.list \
    && apt-get update \
    && apt-get install -y google-chrome-stable


# Selenium-wire dependencies
RUN apt install -y openssl


USER jovyan
WORKDIR /tmp


# Install dependencies
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools
COPY ./requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Docker options
ENV JUPYTER_ENABLE_LAB=yes
ENV GRANT_SUDO=yes


WORKDIR /home/jovyan