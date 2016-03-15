# S3 File Uploader
Basic S3 uploader you would use from your windows CLI.
Displays upload % progress in CLI screen.

##Version

OS|Platform|Version 
---|---|---- | -------------
Windows|64bit|[0.1.0 beta]

##Purpose

- Ad-hoc file upload to AWS S3.
- Optional upload to Reduced Redundancy storage (not RR by default).
- Optional public after upload (private by default)
- Custom S3 Key (defaulted to file name)

##Audience

Business Analysts, AWS Developers, DevOps, 

##Designated Environment
Pre-Prod (UAT/QA/DEV)

##Environment variables

-Set folllowing environment variables:
```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
```

##Example file upload

```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
  
cd c:\tmp\S3_Uploader
s3_percent_upload.exe c:\tmp\data.zip test123 -r -p
Connecting to S3...
File size: 388.5KiB
Public = True
ReducedRedundancy = True
Uploaded 0 bytes of 397799 (0%)
Uploaded 24576 bytes of 397799 (6%)
Uploaded 49152 bytes of 397799 (12%)
Uploaded 73728 bytes of 397799 (18%)
Uploaded 98304 bytes of 397799 (24%)
Uploaded 122880 bytes of 397799 (30%)
Uploaded 147456 bytes of 397799 (37%)
Uploaded 172032 bytes of 397799 (43%)
Uploaded 196608 bytes of 397799 (49%)
Uploaded 221184 bytes of 397799 (55%)
Uploaded 245760 bytes of 397799 (61%)
Uploaded 270336 bytes of 397799 (67%)
Uploaded 294912 bytes of 397799 (74%)
Uploaded 319488 bytes of 397799 (80%)
Uploaded 344064 bytes of 397799 (86%)
Uploaded 368640 bytes of 397799 (92%)
Uploaded 393216 bytes of 397799 (98%)
Upload complete.
Your file is at: https://s3-website-us-west-2.amazonaws.com/test123/data.zip

Time elapsed: 2.54299998283 seconds

```




##Download
* [Master Release](https://github.com/alexbuz/S3_File_Uploader/archive/master.zip) -- `s3_percent_uploader 0.1.0`
