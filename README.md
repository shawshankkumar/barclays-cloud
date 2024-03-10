<div align="center">
  <img alt="Logo" src="https://user-images.githubusercontent.com/73738347/229346352-b23fb62e-274d-4d0c-a90b-47efb34c162d.png" height="56" />
</div>


<br>
<p align="center">
Meet Customer Data Ingestion Pipeline, a cloud native full stack data pipeline built at <a href="https://barclays.com/">Barclays'</a> data stellar hackathon.
</p>
<p align="center">
crafted with <span style="color: #8b0000;">&hearts;</span> by your besties <a href="https://github.com/jhaanupama">Anupama</a> , <a href="https://github.com/mayank1611">Mayank</a>, <a href="https://github.com/whiletrueee">Harshit</a> and <a href="https://github.com/shawshankkumar">Shashank</a>.
</p>
<p align="center">
    <img src="https://img.shields.io/badge/version-1.0.0-yellowgreen" alt="version 1.0.0"/>
    <img src="https://img.shields.io/badge/license-MIT-brightgreen" alt="license MIT"/>
</p>
<br>


## BTW Our team won the hackathon 😜 

**************************

### Team Participants


| <p align="center">![Shashank Kumar](https://github.com/shawshankkumar.png?size=128)<br>[Shashank Kumar](https://github.com/shawshankkumar)</p> | <p align="center">![Harshit](https://github.com/whiletrueee.png?size=128)<br>[Harshit Singh](https://github.com/whiletrueee)</p> | <p align="center">![Anupama Jha](https://github.com/jhaanupama.png?size=128)<br>[Anupama Jha](https://www.linkedin.com/in/anupama-jha-523bb2207/)</p> | <p align="center">![Mayank Jha](https://github.com/mayank1611.png?size=128)<br>[Mayank Jha](https://www.linkedin.com/in/mayank1611/)</p> |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |  ------------------------------------------------------------------------------------------------------------------------------------------------------ | 


**************************

## Tech Stack

![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)
![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB)
![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![AmazonDynamoDB](https://img.shields.io/badge/Amazon%20DynamoDB-4053D6?style=for-the-badge&logo=Amazon%20DynamoDB&logoColor=white)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white)
![Grafana](https://img.shields.io/badge/grafana-%23F46800.svg?style=for-the-badge&logo=grafana&logoColor=white)
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Kaggle](https://img.shields.io/badge/Kaggle-035a7d?style=for-the-badge&logo=kaggle&logoColor=white)
**************************

## Planned Flow diagram:

![dataStellar](https://user-images.githubusercontent.com/73738347/229346933-68070c6d-f443-445f-8a45-38049e167ff7.png)

**************************

## Initial PPT:

[init.pdf](https://github.com/shawshankkumar/barclays-cloud/files/14550730/init.pdf)

## Initial solution:
This is a data management project that involves collecting, processing, and storing data from various sources in a centralized location for further analysis. The Goal of this project is to make data readily available for analysis by extracting data from a variety of sources and integrating it into a single repository, such as a data warehouse

aim:

The aim of this product is to parse and aggregate all customer data into a single database. We aim to process structured data (from an RDBS), unstructured data (from APIs and other sources), and semi-structured data. Additionally, we aim to ensure that our system is as cloud-native as possible, primarily utilizing AWS services with minimal manual intervention. Our objective is to create a pipeline that can handle large files, parse and process them in an event-driven infrastructure, and serve JSON data. Ultimately, our primary objective is to take various types of data, parse and process them, and store them in a designated database for easy access.

Our secondary objective is to provide our fellow developers with as much control as possible. To achieve this, we will implement a logging service to monitor and alert in case of errors and batch failures. We also plan to create a dashboard where different teams and developers in Barclays (or any other organization) can generate secure API keys and create new projects. Each new project will have a separate table and bucket to ensure data isolation. We also plan on giving the option to migrate all of the data from our database (exporting data).Implementation:

We plan to use AWS services as much as possible, with a few exceptions. We have attached a flow diagram to make it easier to understand how our system will work. Everything starts with a NextJS application. We plan to use CloudFlare Zero Trust to ensure that only admins can add new developers. Once a developer is added, they will receive a unique API key that they can use to extract processed data, upload new files, or push data in JSON or other formats.

Since we want all access to be authenticated, we will only allow authorized requests with IP whitelisting and rate limiting. We plan to use NodeJS with Typescript for most of the scripting since the community support is great, and our team is more familiar with it, but we will use Python if we need to perform something that is difficult to do with Node. We plan to use DynamoDB to store our structured and processed data because it is highly scalable, serverless (we do not have to manage anything), and has excellent support for event-driven infrastructure. We can easily connect a Lambda function to process data.

We will use S3 to store BLOB, and we will connect Lambdas to it so that in case of any file uploads or updates, we can trigger that Lambda and parse, process, and insert data into DynamoDB.

Additionally, we plan to use OpenRefine/AWS Glue for ETL and Papertrail for error logging and monitoring. We may choose to go with a different provider, but due to the limited time and our prior experience, we may go with Papertrail.CloudTrail and CloudWatch are also must for AWS services logging and we'll run our APIs on either EC2 with ubuntu or dockerize it and run on something like Fargate with ECS so that we do not have to manage our APIs. AWS API gateway is also in our plans because we need to add rate limit and also control DDOS and other attacks. While our end goal in the pipeline is to store data in Dynamodb, the data might take different paths. If it is a file, it goes on s3 first and then db, if it is coming from a structured or semi-structured source, it gets cleaned and directly transferred to the DB.Application:

Once completed, our pipeline can be used to ingest multiple types of data, process it, and store it in a database, making it easier to query or analyze. It can be customer data, or we can modify it to support other forms of data. Some applications that come to our minds are financial data or healthcare data, where there is a vast amount of PDFs and other health reports that need to be parsed, stored, and analyzed.

For the hackathon, our aim is to build a working prototype and a proof of concept. Once the hackathon is over, we plan to implement changes and work on feedback from mentors and judges to apply them in real life. Some of our teammates are already working as interns at companies where a lot of healthcare or e-commerce data is processed. We will look into the possibilities of using this pipeline to solve issues there.We also plan on adding major support for migration from an RDBMS. Because right now, we will have to send the JSON data from APIs or run a local script, which is not very effective. We plan on using tools like Prima to migrate data at scale!


## Final Flow diagram:

![WhatsApp Image 2023-04-01 at 10 19 21 AM](https://user-images.githubusercontent.com/74819565/229266716-fecb8552-9973-4253-87fb-9d9224c60ebb.jpeg)

## Presentation: 

[BARCLAYS CUSTOMER DATA INGESTION.pdf](https://github.com/shawshankkumar/barclays-cloud/files/11131759/BARCLAYS.CUSTOMER.DATA.INGESTION.pdf)

## Updated Presentation

[For a later presentation at Barclays](https://docs.google.com/presentation/d/106gvkBV2QoVo9UJ9N60LKP_JxAVkZLR23HY4Fn1ZKuM/edit#slide=id.g4dfce81f19_0_45)

## Video Demo :

https://user-images.githubusercontent.com/73738347/229346186-660b5bd8-50ee-47b0-89e3-8dc8997d48bb.mp4

## Updated Video Demo :

https://github.com/whiletrueee/barclays-cloud/assets/74819565/88503df8-e5a5-4d27-bfbf-0b1155c493c8



