FROM node:lts-alpine3.12

# Layer 1, add package.json and install deps.
RUN echo "Building ampproject/toolbox-optimizer"
COPY package.json .
RUN npm install -g pm2
RUN yarn

# Layer 2: add src files
COPY *.js ./

EXPOSE 3000 3001
CMD ["pm2-runtime", "start", "./index.js", "-i", "3"]
