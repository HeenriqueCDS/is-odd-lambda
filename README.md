# AWS Lambda Number Odd Checker

This is a simple AWS Lambda application that receives a number via API Gateway and returns whether it is odd or not.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (with npm)
- [AWS CLI](https://aws.amazon.com/cli/)
- [Terraform](https://www.terraform.io/downloads.html)

## Installation

1. Clone this repository:

    ```bash
    git clone <repository-url>
    ```

2. Navigate to the project directory:

    ```bash
    cd is-odd-lambda
    ```

3. Install dependencies:

    ```bash
    npm install
    ```

## Building the Project

To build the project, run:

```bash
npm run build
```

## Generating Lambda Layer

To generate the Lambda layer, run:

```bash
npm run layer:generate
```

## Deployment

1. Deploy the Lambda function and API Gateway using Terraform:

    ```bash
    terraform init
    terraform apply
    ```

2. After the deployment is complete, note the API Gateway endpoint URL provided by Terraform.

## Usage

To use this application, send a POST request to the API Gateway endpoint with a JSON body containing the number you want to check. Here's an example using cURL:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"number": 7}' <api-gateway-url>
```

Replace `<api-gateway-url>` with the actual URL of your API Gateway endpoint.

## Example Response

If the number is odd, the Lambda function will return:

```json
{
  "message": "The number is odd! :)"
}
```

If the number is even, the Lambda function will return:

```json
{
  "message": "The number is not odd! :("
}
```

## Cleanup

To avoid incurring unnecessary charges, make sure to destroy the AWS resources after you're done using them. You can do this by running:

```bash
terraform destroy
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
