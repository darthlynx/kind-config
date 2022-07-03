# Basic `kind` cluster configuration with the local registry

[Source](https://kind.sigs.k8s.io/docs/user/local-registry/)

> Please keep in mind using exact image version. `kind` [may not work](https://iximiuz.com/en/posts/kubernetes-kind-load-docker-image/) properly with the `latest` image tag for local registry

## Using The Registry

The registry can be used like this.

1. First we'll pull an image `docker pull gcr.io/google-samples/hello-app:1.0`
2. Then we'll tag the image to use the local registry `docker tag gcr.io/google-samples/hello-app:1.0 localhost:5001/hello-app:1.0`
3. Then we'll push it to the registry `docker push localhost:5001/hello-app:1.0`
4. And now we can use the image `kubectl create deployment hello-server --image=localhost:5001/hello-app:1.0`

If you build your own image and tag it like `localhost:5001/image:foo` and then use it in kubernetes as `localhost:5001/image:foo`

