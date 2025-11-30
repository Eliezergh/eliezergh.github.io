+++ 
draft = false
date = 2025-07-02T21:31:32+01:00
title = "AWS Resource Search - Find All Resources in Your AWS Account"
description = "How to find all resources across your AWS account using Tag Editor"
tags = ["aws", "cloud", "devops"]
categories = ["Tutorials"]
+++

Managing resources in AWS can be hard, especially when you have resources spread across multiple regions and services. If you're looking for a way to find all your resources in one place, the **AWS Resource Groups >> Tag Editor** will do the job for you.


## Why Use the AWS Resource Groups >> Tag Editor?

- **Centralized Search:** Find resources across all AWS services and regions from a single interface.
- **Tag Management:** Easily view, add, or edit tags to organize your resources.
- **Cost Optimization:** Identify unused or underutilized resources for cleanup.
- **Security & Compliance:** Ensure resources are properly tagged for auditing and governance.

## How to Search All Resources with AWS Tag Editor

1. **Open the AWS Console:**  
   Go to the [AWS Management Console](https://console.aws.amazon.com/).

2. **Navigate to AWS Resource Groups** service:  
   In the left navigation bar, under **Tagging** section, select **Tag Editor**.

3. **Select Regions:**  
   Choose the regions you want to search. For a complete inventory, select all regions.

4. **Select Resource Types:**  
   You can search for all resource types or filter by specific services (EC2, S3, Lambda, etc.).

5. **Set Tag Filters (Optional):**  
   If you want to find resources with specific tags, set your filters here. To list everything, leave this blank.

6. **Run the Search:**  
   Click **Search resources**. It will take some time depending on the number of resources and regions selected.
   The results will show all matching resources, including their ARNs, types, and tags.

7. **Export Results:**  
   You can export the results to CSV for further analysis or reporting.

## Pro Tip: Use AWS CLI to list resources
If you prefer command-line tools or need to automate this process, you can use the AWS CLI

````bash
aws resourcegroupstaggingapi get-resources --region <region>
````

You'll need to play with the parameters and output format to get the desired results, but this can be a powerful way to script resource management tasks.