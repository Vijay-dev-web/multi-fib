FROM node:16-alpine as builder

WORKDIR /app

COPY packge.json .
RUN npm install
COPY . .

CMD ["npm", "start"]

FROM nginx
EXPOSE 3000
COPY --from=builder /app/build /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/donf.d/default.conf



