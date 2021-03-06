# Frequently Asked Questions (FAQ)

A collection of frequently asked questions with answers!

If you have a question & have found an answer, send a PR to add it here!

## Can I use repo2docker to bootstrap my own Dockerfile?

No, you can't.

If you pass the `--debug` flag to `repo2docker`, it outputs the intermediate
Dockerfile that is used to build the docker image. While it is tempting to copy
this as a base for your own Dockerfile, that is not supported & in most cases
will not work. The `--debug` output is just our intermediate generated
Dockerfile, and is meant to be built in
[a very specific way](https://github.com/jupyter/repo2docker/blob/master/repo2docker/detectors.py#L381).
Hence the output of `--debug` can not be built with a normal `docker build -t .`
or similar traditional docker command.

Check out the [binder-examples](http://github.com/binder-examples/) github
organization for example Dockerfiles you can copy & modify for your own use!
