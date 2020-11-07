# pull official base image
FROM node:13.12.0-alpine

# set working directory
WORKDIR /fe

# install app dependencies
COPY package.json /fe

RUN npm install
RUN npm install react-scripts@3.4.1 -g

# add app
COPY . /fe

# start app
CMD ["npm", "start"]
