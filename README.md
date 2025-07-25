<h2 align="center">
    <img height="200" alt="ecr-push" src="images/header-ecr-push.png" />
    <br>
    ecr-push: for hassle-free docker image deployments to aws ecr
</h2>

---

<div align="center">

<a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.6%2B-blue.svg" alt="Python 3.6+ supported"></a>
[![Last Commit](https://img.shields.io/github/last-commit/DChason/ecr-push.svg)](https://github.com/DChason/ecr-push/commits/main)
[![Issues](https://img.shields.io/github/issues/DChason/ecr-push.svg)](https://github.com/DChason/ecr-push/issues)
[![GitHub stars](https://img.shields.io/github/stars/DChason/ecr-push.svg)](https://github.com/DChason/ecr-push/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20me-LinkedIn-blue?logo=linkedin)](https://www.linkedin.com/in/damienchason/)

</div>

**ecr-push** is a command-line utility for pushing Docker images to AWS Elastic Container Registry (ECR) with minimal hassle. It handles authentication, repository creation, image tagging, and push progress — all in one go.

- Authenticates using your AWS profile
- Creates the ECR repository if it doesn't exist
- Pushes local Docker images to AWS ECR

---

## Requirements

- Python packages: `boto3`, `docker`
- AWS CLI configured with desired profiles
- Docker (installed and running)

Install dependencies:
```sh
pip install -r requirements.txt
```

---

## Installation (Linux or macOS)

**Recommended:**
Clone the repository and copy `ecr-push` to a directory in your PATH:

```sh
git clone https://github.com/DChason/ecr-push.git
cd ecr-push
cp ecr-push /usr/local/bin/
chmod +x /usr/local/bin/ecr-push
```
<br>

**Alternative:**
Download directly via `wget` or `curl`:

```sh
wget https://raw.githubusercontent.com/DChason/ecr-push/main/ecr-push -O /usr/local/bin/ecr-push
chmod +x /usr/local/bin/ecr-push
```

or

```sh
curl -o /usr/local/bin/ecr-push https://raw.githubusercontent.com/DChason/ecr-push/main/ecr-push
chmod +x /usr/local/bin/ecr-push
```

---

## Usage

```sh
ecr-push -p <aws-profile> -a <account-number> -n <image-name> -t <image-tag>
```

**Example:**
```sh
ecr-push -p myprofile -a 123456789012 -n ubuntu -t latest
```

---

## Flags & Options

- `-p`, `--profile`
  - AWS profile name (**required**)
- `-a`, `--account-number`
  - AWS account number (12 digits, **required**)
- `-n`, `--image-name`
  - Docker image name (e.g., 'my-app', **required**)
- `-t`, `--image-tag`
  - Docker image tag (e.g., 'latest', **required**)

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
