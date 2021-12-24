# Jupyter Notebooks

Jupyter Notebooks using [Jupyter Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/)

## Build docker images

Add, remove packages in `requirements.txt` as your need.

```shell
docker build -t notebook-basic ./basic
docker build -t notebook-scrapping ./scrapping
```

## Start notebook

Customize your notes volume and docker container name, port.

```shell
mkdir -p ~/notes
docker run\
    -it --rm --user root\
    -d -p 9000:8888\
    -v ~/notes:/home/jovyan/work/\
    --name notebook\
    -t notebook-basic\
    start-notebook.sh\
    --NotebookApp.token=''\
    --NotebookApp.notebook_dir=/home/jovyan/work

```

If can not open new notebook (File Permission), run following command

```shell
sudo chown -R $USER:$USER <notes-volume>
```
