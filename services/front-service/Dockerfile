FROM node:8.9.3

RUN git clone --branch v2.3.0 https://github.com/21-23/front-end-service.git ./front-end-service
WORKDIR ./front-end-service
COPY ./config.secret*.json ./
RUN npm i --production

RUN git clone --branch v2.3.1 https://github.com/21-23/front-end-service.git ../git
RUN cp -r ../git/* .
RUN npm i --production

COPY ./_qd-ui/dist-prod/* ./static/_qd/
COPY ./cssqd-ui/dist-prod/* ./static/cssqd/
COPY ./jsqd-ui/dist-prod/* ./static/jsqd/

CMD npm run start:container
