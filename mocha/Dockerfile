FROM coderpower/node

# Install modules globally
RUN npm install -g mocha@2.3.4
# Clean modules caches
RUN rm -rf npm_cache /tmp/*

# Set env
ENV NODE_PATH /usr/local/lib/node_modules/
ENV ENGINE mocha
ENV ENGINE_VERSION 2.3.4

# Create /src directory and set it to cwd
RUN mkdir /src
WORKDIR /src

# Create volume with host target directory
RUN mkdir /user

# Install package.json and use the cache of docker to prevent reinstall at every
# build
COPY package.json /dist/package.json
RUN cd /dist && npm install

# Copy exercise repository into image
ADD . /src/

# Link node_modules into the exercise repository
RUN ln -s /dist/node_modules /src/node_modules

# Launch run.sh by default
ENTRYPOINT ["bash", "./run.sh"]
