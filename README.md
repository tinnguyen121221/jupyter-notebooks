# Jupyter Notebooks

Jupyter Notebooks using [Jupyter Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/)

## Build docker images

Add, remove packages in `requirements.txt` as your need.

```
docker build -t notebook-basic ./basic
docker build -t notebook-scrapping ./scrapping
```

## Start notebook

Customize your notes volume and docker container name, port.

```sh
docker run\
    -it --rm --user root\
    -d -p 9000:8888 
    -v ~/notes:/home/jovyan/work/\
    --name notebook\
    -t notebook-basic\
    start-notebook.sh\
    --NotebookApp.token=''\
    --NotebookApp.notebook_dir=/home/jovyan/work

```