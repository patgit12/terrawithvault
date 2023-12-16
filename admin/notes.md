To start vault  i need:
vault address and vault token. Those are provided when vault start in dev mode(the dev mode terminall should always stay up otherwise you'll have to restart)
the command to run vault in dev is: vault server -dev
the token is also store in your home directory as .vault-token

the credentials are storesd in the vault path aws/creds/aws_backend_role (in this case is ec2 admin role). use the commandd vault read aws/creds/aws_backend_role -format json and then with jq you can extract data.access and data.secret( jq -r .data.access jq -r .data.secret) give those new values to aws_key_id and aws_secret_key
