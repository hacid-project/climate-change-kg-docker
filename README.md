# climate-change-kg-docker
Docker setup for Climate Change Knowledge Graph instance

## Get the RDF Dump

Get the RDF dump file in one these two ways:
- download latest release from https://doi.org/10.6084/m9.figshare.29066711
- generate it with the code at https://github.com/hacid-project/climate-change-kg

First method is recommended unless you are a KG developer updating the data source mapping.

## Install Services

```shell
git clone https://github.com/hacid-project/climate-change-kg-docker
cd climate-change-kg-docker
./build-lodview-img.sh
```

## Run

```shell
sudo docker compose up
```

## Create Triple Store

Go to http://keng.istc.cnr.it:7200/repository/create/graphdb.

Create a new repository called `climate-change-kg`.

## Load Data

Go to http://keng.istc.cnr.it:7200/import#user.

Upload the RDF dump to the `climate-change-kg` repository.

## Update SSL Certificate

```shell
sudo docker compose run certbot renew
```

```shell
sudo docker compose restart out-facing
```
