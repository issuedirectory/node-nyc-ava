FROM node:8

RUN echo "Caching NPM files" \
  && npm cache add nyc \
  && npm cache add ava \
  && npm cache add bower \
  && npm cache add sinon \
  && npm cache add express \
  echo "Finished caching files."
