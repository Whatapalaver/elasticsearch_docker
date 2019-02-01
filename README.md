ElasticSearch
=====

Following a [dokerised elasticsearch tutorial](https://blog.patricktriest.com/text-search-docker-elasticsearch/) from Patrick Triest.

## Installation Instructions

- clone this git repo `git clone https://github.com/Whatapalaver/elasticsearch_docker`
- unzip the following to the folder books/ https://cdn.patricktriest.com/data/books.zip

## Running Instructions

- run `docker-compose build` to build the Node.js application
- run `docker-compose up` to launch the application stack or `docker-compose up -d` for background daemon
- Alternatively the shortcut `docker-compose up -d --build` is the equiv of the previous two steps
- visit `localhost:8080` to view the frontend
- visit `localhost:3005` to view message from the Node server
- visit `localhost:9200` to view elasticsearch
- run `docker exec gs-api "node" "server/load_data.js"` to load all the book data into the elastic search container

For changes to backend code you need to rebuild the container but the frontend public directory is mounted to the Nginx fileserver so changes will be reflected automatically.

## Searching

- for the json output visit `http://localhost:3005/search?term=darwin`
- for the Vue.js search console visit `http://localhost:8080/`
