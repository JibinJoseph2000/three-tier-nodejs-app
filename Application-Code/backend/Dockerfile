# Stage 1: Install dependencies
FROM node:14 AS dependencies

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install

# Stage 2: Runtime
FROM node:14

WORKDIR /usr/src/app

COPY --from=dependencies /usr/src/app/node_modules ./node_modules
COPY . .

EXPOSE 3500

CMD ["node", "index.js"]
