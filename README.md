
# Smart portfolio using AWS

#### EXPLORE Data Science Academy Cloud Computing Predict

Check my website: **[Smart Portfolio](https://master.dhu929jn9e771.amplifyapp.com/)**
(Note: It works for the AWS verified mails only so that it wont affect by spam emails. To avoid this we must convert our mail to business mail and approved by AWS.)
## Overview

In this website you will make use of Python and AWS to create an intelligent data science portfolio website. At a high-level, the website will be hosted in a serverless manner on AWS; showcasing your amazing data science, machine learning and AI projects. 

This website will not only teach you the valuable skill of setting up and consuming AWS services to host a website, but it will also teach you how to use these services in creating an intelligent Natural Language Processing (NLP) service. This NLP solution will allow you to automatically populate and send intelligent emails to interested parties based on the messages they send to you through the website. For example, if a potential recruiter sees a particular portfolio project on your website that interests them and contacts you regarding the said project, it is possible to set up your NLP component to pick up what the tone and key phrases are in the recruiter's message. Some smart programming techniques can then be used to automatically send a response. 

<p align="center">
  <img src="https://raw.githubusercontent.com/Explore-AI/Pictures/master/serverless_predict_process.PNG"/>
    <br>
    <em>Figure 1: System Overview</em>
</p>


In **Figure 1** the solutions architecture of this predict is depicted. Below follows a brief description of each module in the system:

>- [x] **[AWS Lambda:](https://aws.amazon.com/lambda/)** A serverless compute instance responsible for multiple processing steps:
>      - Stores the enquiry details within an AWS DynamoDB instance for later retrieval.
>      - Forwards the enquiry contents to AWS Comprehend to help formulate an intelligent response to the site visitor.
>      - Provides logic to formulate an intelligent response based on AWS Comprehend output.
>      - Upon successful completion of these tasks, invokes AWS SES to send emails to the website enquirer and an automated marking email address.
>      
>- [x] **[AWS Amplify:](https://aws.amazon.com/amplify/)** Responsible for serving the static web content hosted in GitHub which becomes the basis of the student web page.
>
>- [x] **[Amazon DynamoDB:](https://aws.amazon.com/dynamodb/)** A NoSQL database responsible for storing enquiry details from individuals visiting the student webpage.
>
>- [x] **[Anazon SES:](https://aws.amazon.com/ses/)** A code-driven email service responsible for returning an intelligent response to webpage visitors based upon their enquiries.
>
>- [x] **[AWS API Gateway:](https://aws.amazon.com/api-gateway/)** AWS service responsible for receiving enquiry details via an API call from the student webpage, and for passing these on to the internal lambda function.
>
>- [x] **[AWS Comprehend:](https://aws.amazon.com/comprehend/)** An intelligent NLP  service capable of characterising sentiment and extracting key-phrases from the ingested text. Used to detect topics within the received webpage enquiries.


## Instructions

The completion of the project involves nine distinct steps which follow on from one another sequentially. This means that you have to completely finish a particular step before you can move on to the next one.


Brief description of each step in the 9-step predict process:

  [Step 1:](#1_section_id) In the first step you will create a **private** fork of this repo that stores all of the code needed to host your static website. 
    
  [Step 2:](#2_section_id) This step is all about customising the static website to suit your needs. You will use the provided bootstrap template and general guides to modify the look and contents of the website to fit your preferences. 
    
  [Step 3:](#3_section_id) In the third step you will use AWS Amplify to serve your modified website. We provide the initial steps to begin this process, and then leave the remainder of the task as an exercise for you to understand and complete. 
  
  [Step 4:](#4_section_id) This step involves the creation of an AWS DynamoDB NoSQL database. This database will be used to store website data as and when visitors send an enquiry. 
    
  [Step 5:](#5_section_id) Here you will create an IAM role that will give your AWS Lambda function (created in step 6) the required permissions to interact with AWS Comprehend, AWS SES, AWS DynamoDB and AWS API Gateway.
    
  [Step 6:](#6_section_id) In this step things get interesting. We set up the AWS Lambda function, a Numpy ARN layer, and an AWS API Gateway trigger:
    
   - **The AWS Lambda Function** will be used to:
        - Write data to Amazon DynamoDB;
        - Generate intelligent email responses with Amazon Comprehend, and
        - Send emails with Amazon SES.

   - **Numpy ARN:**
        - AWS Lambda runs Python on a Linux operating system. This means if you want to use popular libraries such as Numpy in your lambda function, you need to configure your Linux environment accordingly. You can do this by adding layers to your lambda function. In the case of Numpy, you will be adding the relevant layer to your Linux environment.

   - **The AWS API Gateway trigger** configures a publicly accessible HTTP API which listens for POST requests from the webpage. When a request is received, its content is parsed and used to invoke the connected lambda function.   
    
  [Step 7:](#7_section_id) In step seven you will need to configure the Lambda function created previously to write incoming data from the website to the DynamoDB database created in step four.
    
  [Step 8:](#8_section_id) This step involves the configuration of the AWS SES service so that your pipeline can send emails automatically with the help of a Lambda function.
    
  [Step 9:](#9_section_id) In this final step you will be required to complete the NLP portion of the predict with the use of AWS Comprehend and by defining additional program logic. At a high level, AWS Comprehend will be used to extract sentiment and key phrases from a message sent from your static website. Using programming logic, you will then define several helper methods and functions which will enable the population of an automated response if the extracted key phrases and sentiment align to specific operating conditions. 


## Conclusion

If you followed the nine-step process described above correctly, you should now have a fully functioning portfolio website capable of sending intelligent email responses in an automated way. Congrats! 

Following the conclusion of this predict and its assessment, you are free (and we encourage you) to tweak various aspects of the project to personalise it even further.
