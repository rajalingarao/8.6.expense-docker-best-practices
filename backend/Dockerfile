FROM node:20
#FROM node:20.15.0-alpine3.20
#FROM node:20.20.1-alpine3.22
EXPOSE 8080
ENV DB_HOST=mysql
RUN useradd expense
#RUN addgroup -S expense && adduser -S expense -G expense 
RUN mkdir /opt/server
RUN chown expense:expense -R /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
USER expense
CMD ["node","index.js"]


# addgroup -S expense → Creates a system group named expense.
# -S = system group (no login, lower UID/GID range).
# adduser -S expense -G expense → Creates a system user named expense and assigns it to the expense group.
# -S = system user
# -G expense = add the user to the expense group