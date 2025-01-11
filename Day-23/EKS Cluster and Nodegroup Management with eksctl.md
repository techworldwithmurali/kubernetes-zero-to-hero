# EKS Cluster Management with eksctl

## Create a Cluster

```bash
eksctl create cluster \
  --name infra-cluster \
  --region us-east-1 \
  --version 1.30 \
  --vpc-private-subnets subnet-0ab8d3e404d04be99,subnet-0140c441a31b472a4 \
  --without-nodegroup \
  --with-oidc
```

## Create a Nodegroup

```bash
eksctl create nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --nodes 2 \
  --node-private-networking \
  --ssh-access \
  --ssh-public-key Infra \
  --nodes-min 2 \
  --nodes-max 5 \
  --nodes 2 \
  --node-type t2.micro \
  --managed
```

## Scale a Nodegroup

```bash
eksctl scale nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --nodes 1 \
  --nodes-min 1 \
  --nodes-max 1
```

## Upgrade the Cluster

```bash
eksctl upgrade cluster \
  --name infra-cluster \
  --region us-east-1 \
  --version 1.31
```

## Upgrade the Nodegroup

```bash
eksctl upgrade nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --kubernetes-version 1.31
```

## Delete a Nodegroup

```bash
eksctl delete nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes
```

## Delete the Cluster

```bash
eksctl delete cluster \
  --name infra-cluster \
  --region us-east-1
```
