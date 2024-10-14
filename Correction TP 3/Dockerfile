FROM ubuntu
RUN mkdir /usr/web
RUN apt update
RUN apt install -y nodejs npm git
WORKDIR /usr/web
RUN git clone https://github.com/rm-formation/docker-intro-tp1.git
WORKDIR ./docker-intro-tp1
RUN npm i
EXPOSE 5173
CMD npm run dev -- --host
