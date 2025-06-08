version: "3"

services:
  retool:
    image: tryretool/backend:latest
    ports:
      - "3000:3000"
    depends_on:
      - db
    env_file:
      - .env

  db:
    image: postgres:15
    environment:
      POSTGRES_USER: retool
      POSTGRES_PASSWORD: retool
      POSTGRES_DB: retool
    volumes:
      - pgdata:/var/lib/postgresql/data
    ports:
      - "5432:5432"

volumes:
  pgdata:
