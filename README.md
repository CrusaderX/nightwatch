Dockerfile for running Nigthwatch tests under CI. This example for Drone CI but you can
do the same in any other CI system.

```yaml
kind: pipeline
name: default

- name: Run tests
  image: crusaderx2/nigthwatch
  commands:
    - npm install nightwatch --progress=false
    - xvfb-run --server-args='-screen 0, 1024x768x16' node_modules/.bin/nightwatch
```