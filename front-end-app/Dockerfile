FROM nginx:alpine
LABEL org.opencontainers.image.source="https://github.com/alext100/mono-pipline/tree/master/front-end-app"
COPY dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
