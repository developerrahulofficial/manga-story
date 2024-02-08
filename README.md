

**Manga Story ** This is Self Hosted Manga Reading Service

Prerequisites: 
Before you begin, ensure that you have the following prerequisites installed on your system:

Docker : https://docs.docker.com/get-docker/
Git : https://git-scm.com/downloads

Step 1: Clone the Repository
Clone the Teemii GitHub repository to your local machine using the following command:

bash
Copy code
git clone https://github.com/developerrahulofficial/manga-story.git
Step 2: Navigate to the Project Directory
Change your current directory to the Teemii project folder:

bash
Copy code
cd manga-story
Step 3: Build and Start the Containers
Use Docker Compose to build and start the containers. You'll find a ready-to-use example docker-compose.yml file at the root of the project. For your convenience, here it is:

yaml
Copy code
version: "3.8"

services:
  teemii-frontend:
    build: ./app
    ports:
      - "8080:80"
    networks:
      - teemii-network
    environment:
      - VITE_APP_TITLE=Teemii
      - VITE_APP_PORT=80

  teemii-backend:
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
  teemii-data:
    name: teemii-data
To build and start the containers, run the following command:

bash
Copy code
docker-compose up -d
The -d flag runs the containers in detached mode, allowing them to run in the background.

Step 4: Access The Project
Once the containers are running, you can access Teemii in your web browser by navigating to:

http://localhost:8080

Teemii should now be accessible on your local machine.

Stopping and Cleanup
To stop and remove the Teemii containers, use the following command:

bash
Copy code
docker-compose down

Happy reading! 📚✨


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

