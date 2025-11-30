# FROM node:22-slim
# WORKDIR /app
# COPY package*.json ./
# RUN npm install         
# COPY ./server .
# EXPOSE 4000
# CMD ["sh", "-c", "npx sequelize-cli db:migrate && npx sequelize-cli db:seed:all && npm run server-start"]


FROM node:22-slim

# Set root working directory
WORKDIR /app

# Copy dependency files and install (from project root)
COPY package*.json ./
RUN npm install

# Copy only server code (not entire repo)
COPY ./server ./server

# Ensure sequelize CLI knows where node_modules live
ENV NODE_PATH=/app/node_modules
ENV PATH=/app/node_modules/.bin:$PATH
                                

# Expose backend port
EXPOSE 4000

# Run migrations, seeds, and start server
CMD ["sh", "-c", "npx sequelize-cli db:migrate --config server/db/config/config.js --migrations-path server/db/migrations && npx sequelize-cli db:seed:all --config server/db/config/config.js --seeders-path server/db/seeders && npm run server-start"]
