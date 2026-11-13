# Project 6

## Part 1

### Documentation

* Copied over from project 5 The website is a tiny two page site. The files are in [web-content](web-content/).
* The [Dockerfile](Dockerfile) has two lines. The first line starts the Apache server image while the second line copies the contents of web-content into Apaches web directory.
* In the directory that had my docker file I ran: docker build -t cheesecakeischeesy/lb-site:latest, docker login -u cheesecakeischeesy, docker push cheesecakeischeesy/lb-site:latest
* To run the container, I used docker run -d --name testsite -p 8080:80 cheesecakeischeesy/lb-site:latest
* The -d flag runs it in the background, the -p 8080:80 flag connects port 8080 on my computer to port 80 in the container
* To see the site go to http://localhost:8080.

## Part 2

### Documentation

* To make a PAT go to your docker account settings, under personal access token create one with read an writing capabilities.
* To make a github secret just go into the repository settings an under secrets select an action an enter the name of the secret and what it should store.
* For this project the secrets set were my docker username and my docker PAT.
* The workflow runs when a commit is pushed to the main branch
* First it copies over the repo files with checkout, then it logs in with the secrets, then it sets up the build tools using buildx, then it buils the image an sens it to the docker repo
* For this to work in another repo the secrets need to be changed to that of the other repo
* For this to work in another workflow the tag at the bottom needs to be changed
* [link to yml](https://github.com/WSU-kduncan/ceg3120-cicd-tisler3-f26/blob/436cc2dfe99b051be76910d6706afea6662b17a5/.github/workflows/docker-build.yml)
* you can match the commit times from github to docker.
* Running the image without a local copy pulls it from docker hub with the updated info.
* [link to docker hub repo](https://hub.docker.com/repository/docker/cheesecakeischeesy/lb-site/general).

## Part 3

### Documentation

* To see your tags use git tag -l
* To make a tag use git tag -a v1.0.0 
* A normal git push will send the tag to git hub
* The workflow only triggers when a tag is added to a commit
* The make meta step takes the tag data from git and makes tag data for docker using docker/metadata-action, The next step logs into docker, then it sets up to build with buildx, then it builds and pushes
* Changes in workflow require an image change with correct username
* Changes in repo require correct secrets and dockerfile
* [link to yml](https://github.com/WSU-kduncan/ceg3120-cicd-tisler3-f26/blob/436cc2dfe99b051be76910d6706afea6662b17a5/.github/workflows/docker-build.yml)
* To see it working you can use the actions tab to see the releases with tags
* You can see the docker images working by running two different release images at the same time
* [link to docker hub repo](https://hub.docker.com/repository/docker/cheesecakeischeesy/lb-site/general).

## Part 4

### Documentation

