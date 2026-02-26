FROM node:18.18-alpine 

WORKDIR /app

RUN addgroup -S gymflex-group && adduser -S gymflex-user -G gymflex-group

COPY package.json package-lock.json ./

RUN npm ci --omit=dev

COPY . .

RUN chown -R gymflex-user:gymflex-group /app

USER gymflex-user

EXPOSE 3002

CMD ["npm", "start"] 

