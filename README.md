# jekyll_doc_builder
Dockerfiles to create automated jekyll and jekyll-auth environments to build static web documents

Current ruby version installed = 2.3.0
Instructions for usage:
*  Install docker in your environment: Instructions for Windows, Mac and Linux are here: <https://docs.docker.com/engine/installation/>
*  run the `jekyll_doc_builder` image by issuing the following command (Port 4000 is arbitary, choose the port based on where you expect your jekyll website to build. Here the assumption is the jekyll website will run on 0.0.0.0:4000 inside your docker container)

```
docker run -itd -p 4000:4000 --name doc_builder akshshar/jekyll_doc_builder 
```

*  Jump into the docker container

```
docker exec -it doc_builder bash
```

*  Now you can clone the jekyll repo of your choice and run it:

```
git clone https://link/to/your-jekyll-repo
cd your-jekyll-repo/
bundle install
jekyll serve --host 0.0.0.0 --port 4000 --config _config.dev.yml
```

*  The website will be available on your laptop/docker workstation at -->  http://localhost:4000

