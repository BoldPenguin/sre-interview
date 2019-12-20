# Bold Penguin SRE team coding puzzle

The candidate will be given:
1. AWS IAM credentials
2. The name of a "key" bucket
3. The object you will read from the "key" bucket

#### Getting started:
Using your language of choice, use the AWS SDK to read from the file in the "key" bucket. This file contains a dictionary of six buckets matched with a key.

Example:
```
{"bold-penguin-rookery-interview-puzzle-b-onebucket-1s6ourf5eotwp": "910955a907e739b81ec8855763108a29", "bold-penguin-rookery-interview-puzzle-b-twobucket-1utapwdsylc31": "d5e1f5a7f2fe3dab21da19f1c04fbd2b", "bold-penguin-rookery-interview-puzzle-threebucket-6qnry0e29r00": "01b6e20344b68835c5ed1ddedf20d531", "bold-penguin-rookery-interview-puzzle-fourbucket-1rtwi7e6ndzh8": "0b18a3d7b9c43ff1750d2baa4606b8d0", "bold-penguin-rookery-interview-puzzle-fivebucket-mzjj2l2n1yem": "62cc0b4ebb0b57b40778179234246c38", "bold-penguin-rookery-interview-puzzle-b-sixbucket-wrx9eca93cuc": "17c0f75d610ec414e5c9be1a6059b65a"}
```

From there, read from the buckets listed as keys in the above dictionary and print out the corresponding words from the values listed above. The dictionaries in the non-key buckets are formatted as:

```
{"80e61d46bfbab2c3ed45575a4ff6a27a": "tsouris", "f52dea2db92640f8cab216e9b4f63080": "paleate", "3c4bfaa40d9ea1cc3ada29d612d98f52": "cantar", "2af4f3daf6cfc5a70f74c9cbfe9a492c": "origin-myth", "1505e06047591c2ea24a38ad0094b683": "stipple", "5184681ae817e9b9edb251cd40492066": "read-out", "b0a3e72b10bf8b0484532bdb34c0bac8": "composited", "7297e5d5f9dd79f673e5770f0328622d": "vicarages", "910955a907e739b81ec8855763108a29": "be"}
```

Your solution should be along the lines of (pseudocode):

```
for k, v in dict
  data = read from bucket k
  print data[v]
```

Internally, our preference is Python and [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html "Boto3"). In which case, you would pull from S3 with [this](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/s3.html#S3.Client.get_object). However, you can use whatever AWS SDK toolset you would like.
