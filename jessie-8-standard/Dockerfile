FROM node:8

RUN echo "Caching NPM files" \
  && npm cache add nyc \
  && npm cache add ava \
  && echo "Finished caching files."
