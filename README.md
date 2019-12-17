Dockerfile and nightwatch.json files for running Nightwatch tests under CI. This example for Drone CI but you can
do the same in any other CI system. Image contains node v12.13.1 and google-chrome-stable 79.0.3945.

> note that this image DOESN'T contain nightwatch package itself, you should install it

```yaml
kind: pipeline
name: default

- name: Run tests
  image: crusaderx2/nightwatch
  commands:
    - npm install --progress=false
    - xvfb-run --server-args='-screen 0, 1024x768x16' node_modules/.bin/nightwatch
```
