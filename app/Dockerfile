FROM node:alpine

RUN adduser \
    --disabled-password \
    --ingroup node \
    --no-create-home \
    nodeapp

RUN adduser \
    --disabled-password \
    --ingroup node \
    usernode

COPY --chown=nodeapp . /app/

WORKDIR /app/

RUN npm install \
    npm audit fix

USER usernode

EXPOSE 3333

CMD ["npm", "start"]