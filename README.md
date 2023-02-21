# Python Downloader for Minio, S3, http/s

Use this downloader to download from the services quoted.

```
download_from_config(config)
```
The method download_from_config does the work. The config value is a Json of the kind 

```
{
  "type": "type",
  "uri": "link used just in http",
  "path": "path_where_to_save_model",
  "config": {
    "access_key": "access_key",
    "secret_key": "secret_key",
    "BUCKET_NAME": "BUCKET_NAME",
    "OBJECT_NAME": "OBJECT_NAME",
    "references_not_to_provide": [
      "when creating the config json this field must not be passed",
      "https://min.io/docs/minio/linux/developers/python/minio-py.html",
      "https://oak-tree.tech/blog/pandas-minio-uploading-downloading-files"
    ]
  }
}
```
Where type is the service that we want to use.
It is possible to check the services supported calling; 

with config external services:
```
get_servicec_with_config()
```
all the services:

```
get_services()
```
The list returned are the types to use in the type json config.
Uri is the link used just in http/s, path is where the file is going to be saved, pass also the name of the file "./download/project/file_to_down.txt". The config field has 4 important fields used to access resources in minio and s3 the field references_not_to_provide is just a collection of references this field must not be passed if so will be ignored. 

It is possible to print this example json with the following commands

for minio:
```
print_config_minio())
```

for s3:
```
print_config_s3()
```

for http/s:
```
print_config_http()
```

### Requirements
```
pip install minio
pip install boto3
```
