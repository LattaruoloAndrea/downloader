# Downloader for Minio, S3, http/s

Use this downloader to download from the services quoted.

```
download_from_config(config)
```
The method download_from_config does the work. The config value is a Json of the kind 

```
{
  "type": "minio",
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
Uri is the link used just in http/s (when using other services just put a placeholder to not get an Exception that is empty), path is where the file is going to be saved, pass also the name of the file "./download/project/file_to_down.txt". The config field has 4 important fields used to access resources in minio and s3 the field references_not_to_provide is just a collection of references this field must not be passed or it will be ignored. 

It is possible to print this example json with the following commands

for minio:
```
print_obj_from_json(json_minio_example())
```

for s3:
```
print_obj_from_json(json_s3_example())
```

for http/s:

```
print_obj_from_json(json_http_example())

```