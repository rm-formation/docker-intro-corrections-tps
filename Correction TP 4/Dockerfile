FROM ubuntu
RUN apt update
RUN apt install -y nodejs npm git
WORKDIR /usr/web
RUN git clone https://github.com/rm-formation/docker-intro-tp1.git
WORKDIR ./docker-intro-tp1
RUN npm i
RUN npm run build

FROM nginx
WORKDIR /usr/share/nginx
#On supprime le dossier html de base de nginx
RUN rm -r html
#On recréé un dossier html vide
RUN mkdir html
#On copie les fichier du stage 0 (ubuntu) vers le nouveau dossier html
COPY --from=0 /usr/web/docker-intro-tp1/dist/ /usr/share/nginx/html/
EXPOSE 80
