In this exercise, you built your own Dockerfile, where you used:

- the `FROM` instruction to define a base image
- the `RUN` instruction to update your environment and to install a required tool
- the `CMD` instruction to set the default command of your image.

Discover more Dockerfile instructions in the [Dockerfile Reference](https://docs.docker.com/engine/reference/builder/).

You also saw briefly the effect of layer caching. In the next chapters we will see how to leverage layer caching and layer sharing to create more efficient images.