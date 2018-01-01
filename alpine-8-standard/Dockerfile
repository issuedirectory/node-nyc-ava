FROM node:8-alpine

RUN echo "Caching NPM files" \
  && npm cache nyc \
  && npm cache ava \
  echo "Finished caching files."
