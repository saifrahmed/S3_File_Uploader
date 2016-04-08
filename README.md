# S3 File Uploader for Windows CLI.
Basic *file to Amazon-S3* uploader.

Features:
 - No need for Amazon AWS CLI
 - Works from your OS Windows desktop (command line)
 - Logs upload % progress to CLI screen.
 - It's executable (s3_percent_upload.exe)  - no need for Python install
 - It's 32 bit - it will work on any vanilla Windows.
 - Access keys are fed from CLI environment (not command line args)
 - Written using Python/boto/PyInstaller

##Version

OS|Platform|Version 
---|---|---- | -------------
Windows|64bit|[0.1.0 beta]

##Purpose

- Ad-hoc file upload to Amazon S3.
- Optional upload to Reduced Redundancy storage (not RR by default).
- Optional "make it public" after upload (private by default)
- Custom S3 Key (defaulted to transfer file name)

##Audience

Business Analysts, AWS Developers, DevOps, 

##Designated Environment
Pre-Prod (UAT/QA/DEV)

## Amazon S3 data upload price

 - It's free to upload file to Amazon S3.
 - Storage will cost you.


##Usage

```
## Upload file to S3.
##
## Upload % progress outputs to the screen.
##
Usage:
  set AWS_ACCESS_KEY_ID=<you access key>
  set AWS_SECRET_ACCESS_KEY=<you secret key>
  s3_percent_upload.exe <file_to_transfer> <bucket_name> [<s3_key_name>] [<use_rr>] [<public>]
        if <s3_key_name> is not specified, the filename will be used.
        --use_rr -- Use reduced redundancy storage.
        --public -- Make uploaded files public.

        Boto S3 docs: http://boto.cloudhackers.com/en/latest/ref/s3.html

```

##Environment variables

* Set the following environment variables:

```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
```

#Example 

####Upload file to Amazon-S3 Reduced Redundancy storage and make in Publicly accessible


```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
  
cd c:\tmp\S3_Uploader
s3_percent_upload.exe c:\tmp\data.zip test123 --use_rr -public

```
####Result
```
c:\Python35-32\PROJECTS\s3>..\\..\\python s3_percent_upload.py C:\Users\alex_buz\Downloads\instantclient-sqlplus-windows.x64-12.1.0.2.0\instantclient_12_1.zip test1 -r -p
Connecting to S3...
File size: 185.2MiB
Public = True
ReducedRedundancy = True
Uploaded 0 bytes of 194152955 (0%)
Uploaded 10223616 bytes of 194152955 (5%)
Uploaded 20447232 bytes of 194152955 (10%)
Uploaded 30670848 bytes of 194152955 (15%)
Uploaded 40894464 bytes of 194152955 (21%)
Uploaded 51118080 bytes of 194152955 (26%)
Uploaded 61341696 bytes of 194152955 (31%)
Uploaded 71565312 bytes of 194152955 (36%)
Uploaded 81788928 bytes of 194152955 (42%)
Uploaded 92012544 bytes of 194152955 (47%)
Uploaded 102236160 bytes of 194152955 (52%)
Uploaded 112459776 bytes of 194152955 (57%)
Uploaded 122683392 bytes of 194152955 (63%)
Uploaded 132907008 bytes of 194152955 (68%)
Uploaded 143130624 bytes of 194152955 (73%)
Uploaded 153354240 bytes of 194152955 (78%)
Uploaded 163577856 bytes of 194152955 (84%)
Uploaded 173801472 bytes of 194152955 (89%)
Uploaded 184025088 bytes of 194152955 (94%)
Uploaded 194152955 bytes of 194152955 (100%)
Upload complete.
Your file is at: https://s3-website-us-west-2.amazonaws.com/test1/instantclient_12_1.zip

Time elapsed: 538.1886253356934 seconds


```




##Download
* [Master Release](https://github.com/alexbuz/S3_File_Uploader/archive/master.zip) -- `s3_percent_uploader 0.1.0`
