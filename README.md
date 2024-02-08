

**Manga Story ** This is Self Hosted Manga Reading Service

Prerequisites: 
Before you begin, ensure that you have the following prerequisites installed on your system:

Docker : https://docs.docker.com/get-docker/
Git : https://git-scm.com/downloads

Step 1. Clone the Teemii Repository¶
Clone the Teemii GitHub repository to your local machine using the following command:


 git clone https://github.com/dokkaner/teemii.git
Step 2. Navigate to the Teemii Directory¶
Change your current directory to the Teemii project folder:


   cd Project
Step 3. Navigate to the Teemii Directory¶
Use Docker Compose to build and start the Teemii containers. You'll find a ready-to-use example at the root of Teemii. For your convenience, here it is:


version: "3.8"

services:
  teemii-frontend:
    #image: dokkaner/teemii:frontend-latest
    build: ./app
    ports:
      - "8080:80"
    networks:
      - teemii-network
    environment:
      - VITE_APP_TITLE=Teemii
      - VITE_APP_PORT=80

  teemii-backend:
    #image: dokkaner/teemii:backend-latest
    build:
      context: ./server
    volumes:
      - teemii-data:/data
    networks:
      - teemii-network
    environment:
      - EXPRESS_PORT=3000
      - SOCKET_IO_PORT=1555

networks:
  teemii-network:
    driver: bridge
volumes:
  data-volume:
    name: teemii-data
Build and start the Teemii containers:


 docker-compose up -d
The -d flag runs the containers in detached mode, allowing them to run in the background.

Step 3. Access Teemii¶
Once the containers are running, you can access Teemii in your web browser by navigating to:


 http://localhost:8080
Teemii should now be accessible on your Server.

Stopping and Cleanup¶

 docker-compose down


- Manga data and metadata retrieval are facilitated by various sources.
    - [AniBrainAI](https://anibrain.ai/) for AI-driven anime and manga insights.
    - [AniList](https://anilist.co/)
    - [Bato](https://bato.to/)
    - [ComickFun](https://comick.fun/)
    - [Goodreads](https://www.goodreads.com/)
    - [Kitsu](https://kitsu.io/)
    - [MyAnimeList (MAL)](https://myanimelist.net/)
    - [MangaDex](https://mangadex.org/)
    - [MangaKakalot](https://mangakakalot.com/)
    - [MangaPill](https://mangapill.com/)
    - [MangaUpdates](https://www.mangaupdates.com/)
    - [Nautiljon](https://www.nautiljon.com/) 

