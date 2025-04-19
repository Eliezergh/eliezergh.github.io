+++ 
draft = false
date = 2025-04-19T16:39:57+01:00
title = "Secrext - A helm chart to implement AWS ECR in your kubernetes cluster"
+++

Secrext is a custom helm chart to handle Kubernetes External Secret Operator which allow you to renew AWS Elastic Container Registry (ECR) Authorization token automatically.

The chart is designed to be used with the [External Secrets Operator](https://external-secrets.io/) and it will create a Kubernetes secret of type `docker-registry` with the ECR credentials.

I've been working with [Harbor](https://goharbor.io/) and [AWS ECR](https://aws.amazon.com/ecr/) for a while now and I wanted to have a solution to automatically renew the ECR credentials in my Kubernetes cluster.

This has been developed because I needed a solution to re-deploy Harbor images in my Kubernetes cluster and I didn't want to have to manually renew the AWS ECR credentials every 12 hours.

This is a simple solution to have the ECR credentials automatically renewed in your Kubernetes cluster.

You can find the chart and the instructions to install it in my [Secrext-helm-chart - GitHub repository](https://github.com/Eliezergh/secrext-helm-chart).