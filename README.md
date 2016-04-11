# Browserify Docker #
This is a Docker image that has nginx and node+npm `v5.x.0` installed. I use it to deploy webapps built with browserify, but you could use it for anything that requires nginx and node.

It is built using the `official/nginx` image, and installing `nodejs/npm` on top of that.

# How to use it #
In your `Dockerfile`, once you have browserified your code, simply the code into `/usr/share/nginx/html`.

In thisg example the `npm run browserify` task produced the browserified code in `build` directory.

```docker
RUN npm install && \
    npm run browserify && \
    cp -r build/* /usr/share/nginx/html/
```
    
Then you are ready to run your custom Docker container.
