[What is AWS CDK?](https://serverless-stack.com/chapters/what-is-aws-cdk.html)

[AWS CDK in Python](https://docs.aws.amazon.com/cdk/latest/guide/work-with-cdk-python.html)

[AWS CDK and Typescript: Deploy a static React app to S3](https://medium.com/swlh/aws-cdk-and-typescript-deploy-a-static-react-app-to-s3-df74193e9e3d)

[Signup for a AWS Fee Tier](https://aws.amazon.com/free/)

[Get and setup AWS Credentials](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/aws-credentials.html)

[Create IAM User](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html)

[Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

[Installing the AWS SAM CLI - This is an AWS CLI tool that helps you develop, test, and analyze your serverless applications locally](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

[Install AWS CDK](https://docs.aws.amazon.com/cdk/latest/guide/work-with-cdk-python.html)

[Install Docker to test apps locally](https://docs.docker.com/get-docker/)

[Install the Toolkit for VS Code](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/setup-toolkit.html)

python -m ensurepip --upgrade

python -m pip install --upgrade pip

python -m pip install --upgrade virtualenv

pip install aws-cdk

Possible error :
is disabled on this system. For more information, see about_Execution_Policies at
https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ cdk --version
+ ~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

Solution : 
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted


[Understand the key concepts: app, stacks, constructs, L1, L2, and L3 constructs](https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html)

Config command: AWS access key ID, secret access key, and default region (I selected us-east-2) when prompted

aws configure

[Build a Hello World App](https://docs.aws.amazon.com/cdk/latest/guide/hello_world.html)

mkdir step00_hello_cdk

cd step00_hello_cdk

cdk init app --language python

After the app has been created, also enter the following two commands to activate the app's Python virtual environment and install its dependencies.

Linux: source .venv/bin/activate
Windows: .venv\Scripts\activate.bat

python -m pip install -r requirements.txt

cdk ls

python -m pip install aws-cdk.aws-s3

Edit step00_hello_cdk_stack.py in the step00_hello_cdk and add

from aws_cdk import aws_s3 as s3

bucket = s3.Bucket(self, 
    "MyFirstBucket", 
    versioned=True,)

npm run build

cdk synth

cdk deploy

Make changes to add auto deletion policy to delete bucket while deleting the stack

bucket = s3.Bucket(self, "MyFirstBucket", 
            versioned=True,
            removal_policy=core.RemovalPolicy.DESTROY,
            auto_delete_objects=True)

cdk bootstrap

You can go to the AWS CloudFormation console and see that it now lists Step00HelloCdkStack:

https://console.aws.amazon.com/cloudformation/home

You'll also find MyFirstBucket (step00hellocdkstack-myfirstbucketb8884501-r3g3as4wff5f) in the Amazon S3 console.

https://s3.console.aws.amazon.com/s3/home?region=us-east-2#


As per the tutorial now modify the app and distroy it

[Step 00 Class Video in English on Facebook](https://www.facebook.com/zeeshanhanif/videos/10225191381716499)

[Step 00 Class Video in English on YouTube](https://www.youtube.com/watch?v=UpuVx8c0-lA)

[Step 00 Class Video in Urdu on Facebook](https://www.facebook.com/zeeshanhanif/videos/10225203759985948)

[Step 00 Class Video in Urdu on YouTube](https://www.youtube.com/watch?v=xWF-LCTnSy4)

# Welcome to your CDK Python project!

This is a blank project for Python development with CDK.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

This project is set up like a standard Python project.  The initialization
process also creates a virtualenv within this project, stored under the `.venv`
directory.  To create the virtualenv it assumes that there is a `python3`
(or `python` for Windows) executable in your path with access to the `venv`
package. If for any reason the automatic creation of the virtualenv fails,
you can create the virtualenv manually.

To manually create a virtualenv on MacOS and Linux:

```
$ python -m venv .venv
```

After the init process completes and the virtualenv is created, you can use the following
step to activate your virtualenv.

```
$ source .venv/bin/activate
```

If you are a Windows platform, you would activate the virtualenv like this:

```
% .venv\Scripts\activate.bat
```

Once the virtualenv is activated, you can install the required dependencies.

```
$ pip install -r requirements.txt
```

At this point you can now synthesize the CloudFormation template for this code.

```
$ cdk synth
```

To add additional dependencies, for example other CDK libraries, just add
them to your `setup.py` file and rerun the `pip install -r requirements.txt`
command.

## Useful commands

 * `cdk ls`          list all stacks in the app
 * `cdk synth`       emits the synthesized CloudFormation template
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk docs`        open CDK documentation

Enjoy!
