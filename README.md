# CDK-ALB

![Assessment tests](https://github.com/nib-health-funds/cdk-alb/actions/workflows/lint-test.yml/badge.svg)

This example creates an AutoScalingGroup (containing a Micro-T2 EC2 instance running Amazon Linux AMI), and an ApplicationLoadBalancer inside a shared VPC. It hooks up an open listener from the Load Balancer to the Scaling Group to indicate how many targets to balance between.

## How to Build

To build this app, you need to be in this example's root folder. Then run the following:

```bash
$ npm install
$ npm run build
```

This will install the necessary CDK, then this example's dependencies, and then build your TypeScript files and your CloudFormation template. For the purpose of the assessment you won't need to compile down to javascript, both the linter and tests can process typescript.

## How to test

```bash
$ npm run lint
$ npm run test
```

🤫 or just commit and push letting the CI run do it for you

## Tasks

Create a PR with the following changes:

1. Update the instance type to something more modern `t3a`
2. Open up 3 additional ports outbound on the ec2 (`5432`, `6379`, `12001`)
3. Change the Autoscaling group to scale on CPU load.
4. Add IAM role to read from the s3 bucket `arn:aws:s3:::cdk-alb-test`
5. Add a script in userdata to copy the `testFile.txt` file from s3 to the new instance.

Success can be measured by the tests passing and/or by the interview panel.

### Help

The [aws-cdk docs](https://docs.aws.amazon.com/cdk/api/v1/docs/aws-construct-library.html) are your best source for help. Also general googleing and stack overflow searching is allowed. We are as much interested in the process as in the results.

Additionally we find the ESLint and Jest plugins to VSCode to be excellent.
