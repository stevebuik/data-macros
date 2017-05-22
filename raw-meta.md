# Editing Meta-Data without a UI

This type of data management is done all the time but....it can be difficult to read

```
{
  "Statement":[{
  "Effect":"Allow",
     "Action":["s3:ListBucket","s3:GetObject","s3:GetObjectVersion"],
        "Resource":["arn:aws:s3:::my_bucket/*","arn:aws:s3:::my_bucket"]
     }
  ],
  "Statement":[{
  "Effect":"Allow",
     "Action":["s3:ListBucket","s3:GetObject","s3:GetObjectVersion"],
        "Resource":["arn:aws:s3:::my_other_bucket/*","arn:aws:s3:::my_other_bucket"]
     }
  ],
  "Statement":[{
  "Effect":"Allow",
    "Action":["s3:ListAllMyBuckets"],
	"Resource":"*",
	"Condition": {} 
     }
  ]
}
```



