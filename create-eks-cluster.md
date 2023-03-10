Create a cluster on AWS eks

export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>
export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>
export AWS_DEFAULT_REGION=us-east-1

eksctl create cluster \
  --version 1.23 \
  --region us-east-1 \
  --node-type t3.medium \
  --nodes 5 \
  --nodes-min 1 \
  --nodes-max 5 \
  --name my-first-cluster
