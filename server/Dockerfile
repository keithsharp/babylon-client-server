FROM 15.12.0-alpine3.13

# Change the PORT number to whatever is appropriate, default is 4000
# Build: docker build --rm -t babylon-ws-server .
# Run: docker run -ti --rm -p 4000:4000 babylon-ws-server

RUN apk update

WORKDIR /app

# copy configs to /app folder
COPY package*.json ./
COPY tsconfig.json ./
COPY src /app/src
RUN npm install
RUN npm run build

EXPOSE 4000

CMD [ "node", "./dist/index.js" ]