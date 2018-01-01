FROM node:8

RUN echo "Caching NPM files" \
  && npm cache nyc \
  && npm cache ava \
  echo "Finished caching files."
