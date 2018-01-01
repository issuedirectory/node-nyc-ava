FROM node:8

RUN echo "Caching NPM files" \
  && npm cache nyc \
  && npm cache ava \
  && npm cache bower \
  && npm cache sinon \
  && npm cache express \
  echo "Finished caching files."
