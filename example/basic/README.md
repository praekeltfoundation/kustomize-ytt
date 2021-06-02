# basic example

This is a simple example that generates a Deployment and Service from `ytt`
templates.

From the repo root, it can be run as follows:
```
export KUSTOMIZE_PLUGIN_HOME=$(pwd)/kustomize/plugin
(cd example/basic/;  kustomize build --enable-alpha-plugins)
```
