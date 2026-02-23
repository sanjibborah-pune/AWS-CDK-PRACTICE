# private-ec2-ssm-igw-nat-cdk

This repository contains an AWS CDK (Python) project that provisions private EC2 instances with SSM access, an Internet Gateway, and NAT Gateway configuration.

This README documents how to run this repository and also provides step-by-step instructions for creating a new AWS CDK Python project from scratch.

**Prerequisites**

- Install Node.js (for the CDK CLI) and npm
- Install Python 3.8+ and `python` available on PATH
- Install the AWS CLI and configure credentials (`aws configure`)
- Install the AWS CDK Toolkit (v2):

```powershell
npm install -g aws-cdk
cdk --version
```

**Quick start — run this repository (Windows PowerShell)**

1. Clone or open this repo and change to its root directory (where `app.py` lives).

2. Create and activate a Python virtual environment:

```powershell
# create venv
python -m venv .venv
# activate venv (PowerShell)
.venv\Scripts\activate
```

3. Install Python dependencies (this repository includes `requirements.txt`):

```powershell
pip install -r requirements.txt
# optionally install dev deps
pip install -r requirements-dev.txt
```

4. Ensure your AWS credentials and default region are configured:

```powershell
aws configure
```

5. (Optional) Bootstrap the environment if not already bootstrapped:

```powershell
# Example: replace <ACCOUNT_ID> and <REGION> or use default environment
cdk bootstrap --profile profilename
```

6. Synthesize the CloudFormation template:

```powershell
cdk synth
```

7. Review changes with a diff:

```powershell
cdk diff
```

8. Deploy the stack:

```powershell
# Deploy all stacks in the app
cdk deploy --all
# or deploy a specific stack by name
cdk deploy PrivateEc2SsmIgwNatCdkStack
```

9. Tear down:

```powershell
cdk destroy --all
```

**Run tests**

This repo includes unit tests under `tests/` using `pytest`.

```powershell
# with venv activated
pip install -r requirements-dev.txt
pytest -q
```

**Create a new AWS CDK Python project (step-by-step)**

1. Create a new directory and initialize a CDK Python app:

```powershell
mkdir my-cdk-app
cd my-cdk-app
cdk init app --language python
```

2. Create and activate a Python virtual environment, then install the generated `requirements.txt`:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

3. Add constructs or the `aws-cdk-lib`/`constructs` packages as needed (if not present in `requirements.txt`):

```powershell
pip install aws-cdk-lib constructs
```

4. Edit `app.py` and stack files under the generated package to define resources. The CDK app entrypoint is `app.py` and stacks live in the package folder (e.g., `my_cdk_app/my_cdk_app_stack.py`).

5. Bootstrap (if needed), synth, diff, and deploy as shown above:

```powershell
cdk bootstrap
cdk synth
cdk diff
cdk deploy
```

**Repository structure (key files)**

- `app.py` — CDK app entrypoint used by the CDK CLI.
- `private_ec2_ssm_igw_nat_cdk/private_ec2_ssm_igw_nat_cdk_stack.py` — the stack implementation.
- `requirements.txt` — Python runtime dependencies.
- `requirements-dev.txt` — development/test dependencies.
- `tests/` — unit tests (pytest).

**Notes & tips**

- Use `cdk synth` to verify generated CloudFormation before deploying.
- Use `cdk diff` to preview changes to your AWS environment.
- When updating Python dependencies, re-create or re-activate the virtualenv to avoid mismatches.
- If you hit permission or role errors during `cdk bootstrap` or `cdk deploy`, ensure the AWS credentials used have sufficient permissions.

If you want, I can also add a simple CONTRIBUTING or developer quickstart file, or run the tests and confirm the README works with actual commands in this environment.
# Welcome to your CDK Python project!

This is a blank project for CDK development with Python.

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
them to your `requirements.txt` file and rerun the `python -m pip install -r requirements.txt`
command.

## Useful commands

 * `cdk ls`          list all stacks in the app
 * `cdk synth`       emits the synthesized CloudFormation template
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk docs`        open CDK documentation


