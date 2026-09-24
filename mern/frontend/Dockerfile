from node:18.9.1-alpine

WORKDIR /app

copy package.json  ./

run  npm install


expose 5173

copy . .

cmd ["npm", "run", "dev"]