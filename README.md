# docker-images

These are some dockerfiles I use everyday.

Nothing fancy, everything could be improved. Open an issue if you like to make a suggestion.

Content:
octopress: docker image to install a base version of octopress, to publish you content in a static way (github pages)
scala and gradle: docker image to install scala and gradle to give you a development environment

To list all stopped containers:
`docker ps -a -q`

To remove all stopped containers:
`docker rm $(docker ps -a -q)`

To build one of the docker files:
``
