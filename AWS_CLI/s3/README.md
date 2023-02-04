## CLI commands for s3


### 1.List all buckets

```powershell
aws s3 ls

```

### 2.Create a new bucket with unique name

```powershell
aws s3 mb "s3://<your_bucket_name>"

```

You can also specify the region using `--region <region_name>`

_example_

```bash
aws s3 ls s3://my-bucket --region ap-south-1

```

### 3.Delete an empty s3 bucket

```bash
aws s3 rb s3://mybucket
```
Replace my bucket with your bucket name.

If the bucket is not empty we can use `--force` parameter to delete all objects first and then 
delete the bucket.

```bash

aws s3 rb s3://mybucket --force

```

### 4.Delete s3 objects

```bash

aws s3 rm s3://mybucket/file.txt 

```

To delete all objects in a bucket we can use `--recursive` parameter.

```bash
aws s3 rm s3://mybucket --recursive
```

### 5.Copy a local file to s3

```bash

aws s3 cp <file_name> s3://mybucket/test2.txt

```

To copy a file from s3 to s3 

`
aws s3 cp <source_bucket/file_name> <dest_bucket/key>
`

_example_

```bash

aws s3 cp s3://mybucket/test.txt s3://mybucket/test2.txt

```
To recursively copy all the objects of a bucket to another bucket

```bash

aws s3 cp s3://source-bucket/ s3://dest-bucket/ --recursive

```

To copy s3 object to local file

```bash

aws s3 cp s3://mybucket/test.txt test2.txt

```

To copy all the objects to local directory use the `--recursive` parameter.

```bash
aws s3 cp s3://mybucket . --recursive
```

To set the ACL while copying the objects

```bash

aws s3 cp s3://src_bucket/test.txt s3://dest_bucket/test2.txt --acl public-read-write

```

### 6.List all the objects in a specific bucket

```bash

aws s3 ls "s3://<bucket_name>"

```


