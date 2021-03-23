# practice-music-scales

I play piano and wanted to devise a way to make practicing scales more fun and challenging. One way to increase the level of difficulty is to play all the major and minor scales in a random order instead of following the circle of fifths. This forces you to better learn each scale in isolation rather than relying on the familiar pattern of adding an additional sharp or flat as you go around the circle of fifths.

To accomplish this goal, this repository contains an AWS Lambda function in Go invoked via an API Gateway endpoint. The Go handler returns a JSON response with both major and minor scales in a random order for practice. The Lambda function and API Gateway are deployed to AWS with a Terraform stack.

With the API endpoint in place, a good next step would be to write a front-end in React. The UI could contain a refresh button to call the back-end API again and present the new randomized scale order to the user.

## How to build the AWS Lambda Go function

See [GitHub AWS Lambda Go repo](https://github.com/aws/aws-lambda-go) for more information. The bash script in the deploy directory builds the Go executable and zips it up prior to handling the Terraform deployment:

```
cd deploy
./_deploy.bash create
```

To destroy the deployment, run the bash script again with a destroy argument:

```
cd deploy
./_deploy.bash destroy
```
