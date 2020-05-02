FROM klakegg/hugo:ext-debian

# upgrade all packages
RUN apt-get update -y
RUN apt-get update -y

RUN npm install -g firebase-tools

COPY ./hugo-firebase /bin
RUN chmod +x /bin/hugo-firebase
RUN /bin/hugo-firebase

ENTRYPOINT [ "/bin/hugo-firebase" ]