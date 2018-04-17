# Usages

```
$ cat auth.json

{
    "type": "TOKEN",
    "methodArn": "arn:aws:execute-api:ap-southeast-2:123456789012:abcdefg123/dev/POST/service/version/endpoint",
    "authorizationToken": "test"
}

$ sam local invoke --event auth.json

2018/04/17 10:49:48 Successfully parsed template.yaml
2018/04/17 10:49:48 Connected to Docker 1.35
2018/04/17 10:49:49 Fetching lambci/lambda:nodejs8.10 image for nodejs8.10 runtime...
nodejs8.10: Pulling from lambci/lambda
Digest: sha256:a53fceb64e2339332dbc4117be8ec270f46fbe28d564499f1cf73035a1c5854e
Status: Image is up to date for lambci/lambda:nodejs8.10
2018/04/17 10:49:52 Invoking index.handler (nodejs8.10)
2018/04/17 10:49:52 Mounting /Users/bill/study/github/serverless-projects/aws-sam-examples/samples_2/api-gateway-authorizer-nodejs as /var/task:ro inside runtime container
START RequestId: 8c6e0cd9-eb15-1969-840b-e0b421b0f617 Version: $LATEST
2018-04-17T00:49:59.322Z	8c6e0cd9-eb15-1969-840b-e0b421b0f617	Loading function
2018-04-17T00:49:59.323Z	8c6e0cd9-eb15-1969-840b-e0b421b0f617	Client token: test
2018-04-17T00:49:59.323Z	8c6e0cd9-eb15-1969-840b-e0b421b0f617	Method ARN: arn:aws:execute-api:ap-southeast-2:123456789012:abcdefg123/dev/POST/service/version/endpoint
END RequestId: 8c6e0cd9-eb15-1969-840b-e0b421b0f617
REPORT RequestId: 8c6e0cd9-eb15-1969-840b-e0b421b0f617	Duration: 12.28 ms	Billed Duration: 100 ms	Memory Size: 256 MB	Max Memory Used: 33 MB

{"principalId":"user|a1b2c3d4","policyDocument":{"Version":"2012-10-17","Statement":[{"Action":"execute-api:Invoke","Effect":"Deny","Resource":["arn:aws:execute-api:ap-southeast-2:123456789012:abcdefg123/dev/*/*"]}]},"context":{"key":"value","number":1,"bool":true}}

```
