# ☁️ dstvsk.com.br
### What is this repository?
In this repository you will find everything that makes my personal blog, dstvsk.com.br, from the CloudFormation template to the Hugo project setup.
- `src` folder: Hugo setup using blowfish theme.
- `templates` folder: Holds the AWS CloudFormation templates that creates the stacks in my AWS account.

### Running the Hugo project locally
- First we move to the folder `cd src`
- Verify if we have hugo installed typing `hugo version` in CLI, if we don't we can install it using `sudo apt install hugo` if you are using Debian distro.
- Then we just run `hugo server` and we should be able to access it https://localhost:1313

### CloudFormation
We use CloudFormation to provision the infrastructure holding this website in AWS.
I tend to use more cli instead of the web interface but you can use the same templates for that also.
```bash
# Check if the CLI client is connected
aws sts get-caller-identity
# Create stack
aws cloudformation create-stack --stack-name dstvsk-env --template-body file://./templates/dstvsk-env.yml
# Update stack
aws cloudformation update-stack --stack-name dstvsk-env --template-body file://./templates/dstvsk-env.yml
```

