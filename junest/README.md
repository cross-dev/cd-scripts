Builds a minimal JuNEST image with few extra-packages necessary for cross-dev.

## Environment

* S3 uploader role, sample policy:
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "UploadToCrossdev",
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:PutObject",
                "s3:PutObjectAcl",
                "s3:CreateMultipartUpload"
            ],
            "Resource": [
                "arn:aws:s3:::crossdev/*"
            ]
        }
    ]
}
```
* S3 uploader role, trusted entities include: `ec2.amazonaws.com`
* EC2 micro-instance with S3 uploader role
* ArchLinux AMI
* Remove `ec2` repository from `/etc/pacman.conf`
* Do preparations according to [README](https://github.com/cross-dev/junest-builder/blob/master/README)

## Running

Execute `junest` script and it will build the minimal image for you and upload it into S3.
