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

*To make a PAT go to your docker account settings, under personal access token create one with read an writing capabilities.
