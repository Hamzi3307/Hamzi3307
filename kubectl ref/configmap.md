## Configmap

- A ConfigMap is an API object used to store non-confidential data in key-value pairs. Pods can consume ConfigMaps as environment variables, command-line arguments, or as configuration files in a volume.

- A ConfigMap allows you to decouple environment-specific configuration from your container images, so that your applications are easily portable.

# ConfigMap does not provide secrecy or encryption.

## Flags

# from-env-file:
- Specify the path to a file to read lines of key=val pairs to create a configmap (i.e. a Docker .env file).
# from-file
- Key file can be specified using its file path, in which case file basename will be used as configmap key, or optionally with a key and file path, in which case the given key will be used. Specifying a directory will iterate each named file in the directory whose basename is a valid configmap key.
# from-literal
- Specify a key and literal value to insert in configmap (i.e. mykey=somevalue)

## Examples:
> Create a new config map named my-config based on folder bar

    - kubectl create configmap my-config --from-file=/root/bar

> Create a new config map named my-config with specified keys instead of file basenames on disk

    - kubectl create configmap my-config --from-file=key1=file1.txt --from-file=key2=file2.txt

> Create a new config map named my-config with key1=config1 and key2=config2

    - kubectl create configmap my-config --from-literal=key1=config1 --from-literal=key2=config2

> Create a new config map named my-config from the key=value pairs in the file

    - kubectl create configmap my-config --from-file=/root/file.txt

> Create a new config map named my-config from an env file

    - kubectl create configmap my-config --from-env-file=path/to/bar.env
