# Learn to retreive AWS secrets and parameters store value

1.  Create a github repository and clone locally.
2.  Add repository secrets and variables got github action to login AWS.
3.  Create **AWS secrets manager- Secrets** and **AWS System Manager – Parameter Store** on AWS console.
4.  Using AWS CLI command to retrieve from secret value.
    ```
        aws secretsmanager get-secret-value --secret-id <SECRET_NAME> --query SecretString --output json | jq -r '. | fromjson | .<Secret.Key>'
    ```
5.  Using AWS CLI command to retrieve parameter store value.
    ```
        aws ssm get-parameter --name <PARAMETER_NAME> --query <Parameter.Value> --output text
    ```
6.  Git push github actions workflows **(yaml file)** to retrieve the both value.
7.  Verify the value should be match on AWS secret manager and parametes store.
