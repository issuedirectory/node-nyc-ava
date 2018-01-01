FROM node:8-alpine

RUN echo "Caching NPM files" \
  && npm cache add nyc \
  && npm cache add ava \
  && npm cache add bower \
  && npm cache add sinon \
  && npm cache add express \
  echo "Finished caching files."
