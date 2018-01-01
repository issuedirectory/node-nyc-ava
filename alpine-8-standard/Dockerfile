FROM node:8-alpine

RUN echo "Caching NPM files" \
  && npm cache add nyc \
  && npm cache add ava \
  && echo "Finished caching files."
