#import image and its version
FROM node

#set working directory
WORKDIR /app

#copy and run config info from package.json and install modules, this is separated due to fact that when rebuilding the container, if this was done earlier avoid unnucessery repetition
COPY package.json .

RUN npm install

#copy all
COPY . .

#make port available for usage
EXPOSE 8081

#command to start
CMD ["node", "index.js"]

