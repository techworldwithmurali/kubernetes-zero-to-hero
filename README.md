# 25 Days of Kubernetes Learning Path

## Day 1 - Kubernetes Overview

- What is Kubernetes
- Why Kubernetes
- Advantages of Kubernetes
- Kubernetes Architecture

## Day 2 - Tools Installation

- Installation of AWS CLI in Windows
- Installation of AWS CLI in Linux
- Installation of AWS CLI in Ubuntu
- Creation of AWS IAM User
- Install kubectl CLI in Windows
- Install kubectl CLI in Linux
- Install eksctl CLI in Windows
- Install eksctl CLI in Linux

## Day 3 - Getting Started with Amazon EKS

- Introduction about AWS EKS
- Creation of AWS EKS Cluster
- Adding Worker Nodes to EKS Cluster
- How to Connect to an Amazon EKS Cluster Using CLI
- Deleting an Amazon EKS Cluster

## Day 4 - Kubernetes Basics

- Kubernetes Objects and API Versions
- Lab Session - Creating a Pod Using Imperative Commands in Kubernetes
- Lab Session - Creating Pods with YAML using Declarative Syntax
- Developing Kubernetes Manifest Files using Editor
- Lab Session - Deployments
- Lab Session - Updating and Rolling Back Deployments

## Day 5 - Kubernetes Namespace

- What is Kubernetes Namespace
- Lab Session - Creating and deleting Kubernetes Namespace
- Deploy the sample application in specific namespace
- What are Resource Quotas?
- Why use Resource Quotas for resource management?
- Resource Quotas vs. LimitRanges

## Day 6 - Kubernetes Services

- What are Kubernetes Services
- Types of Kubernetes Services
- What is ClusterIP
- Lab Session - ClusterIP
- Lab Session - NodePort
- Lab Session - Load Balancer

## Day 7 - Kubernetes Ingress Controller

- What is Kubernetes Ingress Controller
- Ingress Controller Features
- Lab Session - Installing and Configuring an Ingress Controller
- Lab Session - Deploy Sample Ingress Resource
- Lab Session - Deploy Sample Ingress Resource with SSL
- Lab Session - Deletion of Sample Ingress Resource

## Day 8 - Kubernetes ExternalDNS

- What is ExternalDNS?
- Why we use ExternalDNS?
- Lab Session - Deploy External DNS in Kubernetes
- Lab Session - Clean up External DNS in Kubernetes

## Day 9 - Kubernetes ConfigMaps and Secrets

- Introduction to Kubernetes ConfigMaps
- Lab Session - Kubernetes ConfigMaps
- Introduction to Kubernetes Secrets
- Lab Session - Kubernetes Secrets

## Day 10 - Kubernetes DaemonSets & StatefulSets

- What are Kubernetes DaemonSets
- Purpose of DaemonSets
- Lab Session - Deploying DaemonSets
- Lab Session - Clean up DaemonSets
- What is Kubernetes StatefulSets
- Use Cases for StatefulSets
- Lab Session - Kubernetes StatefulSets

## Day 11 - Kubernetes Volumes

- Overview of Volumes
- Types of Volumes
- What is Persistent Volumes and Claims
- Lab Session - Provisioning and Managing PVs and PVCs
- What is Storage Classes
- Lab Session - Storage Classes

## Day 12 - Resource Monitoring using Metrics Server & HPA

- What is Metrics Server
- Metrics Server Architecture
- Resource Metrics in Kubernetes
- Lab Session - Installation and Configuration of Metrics Server
- Introduction to Horizontal Pod Autoscaling (HPA)
- Lab Session - Creating and Managing HPA Resources

## Day 13 - Kubernetes Cluster AutoScaler

- What is Cluster Autoscaler
- Create IAM OIDC provider
- Create IAM policy for Cluster Autoscaler
- Create IAM role for Cluster Autoscaler
- Deploy Kubernetes Cluster Autoscaler
- Create an Nginx deployment to test the Cluster Autoscaler functionality

## Day 14 - Kubernetes Probes

- What are Probes in Kubernetes
- Types of Probes (Readiness, Liveness)
- Lab Session - Configuring Readiness Probes
- Lab Session - Configuring Liveness Probes

## Day 15 - RBAC in Kubernetes

- What is RBAC in Kubernetes?
- RBAC components: Roles, RoleBindings, ClusterRoles, and ClusterRoleBindings
- What is Role and RoleBinding in Kubernetes
- Lab Session - Creating and testing Roles and RoleBindings
- What are ClusterRoles and ClusterRoleBindings
- Lab Session - Creating and testing ClusterRoles and ClusterRoleBindings

## Day 16 - Logging in Kubernetes

- Explanation of EFK: Elasticsearch, Fluentd, Kibana
- What is Elasticsearch?
- What is Kibana?
- Lab Session - Setting up Elasticsearch and Kibana in AWS
- What is Fluentd?
- Lab Session - Deploying Fluentd as a Daemonset for Log Collection and sending logs to Elasticsearch

## Day 17 - Monitoring in Kubernetes

- What is Monitoring in Kubernetes
- What is Prometheus
- What is Grafana?
- Installation of Prometheus and Grafana using Helm Chart

## Day 18 - Kubernetes Taints and Tolerations

- What are Taints and Tolerations
- Lab Session - Applying Taints to Nodes
- Creating Toleration Specifications
- Lab Session - Implementing Taints and Tolerations
- Node Affinity and Node Anti-Affinity in Kubernetes
- Lab Session - Implementing Node Affinity and Node Anti-Affinity

## Day 19 - Kubernetes Project 1

- Deploy the application to EKS fetching image from AWS ECR

## Day 20 - Kubernetes Project 2

- Deploy the application to EKS, fetching the image from DockerHub

## Day 21 - Kubernetes Project 3

- How to Deploy Argo CD on Kubernetes

## Day 22 - EKS Upgrade Process

- Preparing for EKS Upgrade
- Lab Session - Upgrading AWS EKS

## Day 23 - Exploring Various Methods for Creating AWS EKS Clusters

- Lab Session - Setting Up AWS EKS with eksctl

## Day 24 - Kubernetes Troubleshooting Part 1

- Pod is in CrashLoopBackOff state. How do you troubleshoot and resolve it?
- Service is not accessible externally. How do you troubleshoot?
- Node is Not Ready. How do you investigate?

## Day 25 - Kubernetes Troubleshooting Part 2

- Pod is stuck in Pending state. How do you troubleshoot and resolve it?
- Container image pull is failing with image not found or access denied errors. How do you troubleshoot and resolve this issue?
