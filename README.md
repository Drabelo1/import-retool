version: '3'
services:
  retool-backend:
    image: tryretool/backend:3.24.2
    environment:
      - NODE_ENV=production
    ports:
      - "3000:3000"

  retool-frontend:
    image: tryretool/frontend:3.24.2
    depends_on:
      - retool-backend
    ports:
      - "3001:3001"

  retool-db-connector:
    image: tryretool/db-connector:3.24.2
    ports:
      - "3002:3002"
