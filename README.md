# MongoRestore.py

-- Note: This script is meant to be used in tandem with [MongoBackup](https://github.com/pmorgan3/MongoBackup "Link to MongoBackup")


This script fetches a mongo backup dump stored in min.io and runs mongorestore on the given database backup.

## Getting Started


### Prerequisites

To use this script you need:

 - Python3.7.7 or later
 - [MongoDB CLI tools](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/ "link to download mongodb tools")


### Installation

Run ``` pip3 -r requirements.txt ```

### Usage
Running the script is simple.

Simply type
```
python3 MongoRestore.py --file=credentials.txt
```

credentials.txt can be named anything but it should look like this:

```
access=your_minio_access_key
secret=your_minio_secret_key
Endpoint=your_minio_endpoint
BucketName=your_minio_bucket_name
database=your_db_name
port=your_db_port
MongoHost=mongo_hostname
User=mongo_admin_username
Password=mongo_admin_password
ZipName=the_backup_zip_folder_name
```

If you want to use environment variables instead of pasting your information in plain text, run the script using the ```-e``` or  ```--environment``` flags. And have your credentials.txt file store your variable names instead of their values. 

If you want to connect to a DB with ssl enabled, pass in the ```-s``` or ```--ssl``` flags.

If your Minio Server requires an SSL connection, pass in the ```--minioSSL``` flag.

## Deployment

This script is built to run on most unix systems. As long as you have a unix based terminal and mongodb tools installed you should be fine.


## License

This project is licensed under the Apache 2.0 License - see the [Full License](https://www.apache.org/licenses/LICENSE-2.0) for details
