FROM node:16-alpine
WORKDIR /lightfeather
COPY package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "start"]
EXPOSE 8080