FROM public.ecr.aws/docker/library/node:18-alpine

WORKDIR /app

COPY package.json ./

RUN npm install --production

COPY server.js .
COPY db.json .

RUN addgroup -g 1001 -S nodejs && \
    adduser -S nodejs -u 1001 && \
    chown -R nodejs:nodejs /app

USER nodejs

EXPOSE 3000
CMD ["node", "server.js"]