# Image-Resizing-Pipeline-with-AWS-S3-Lambda-and-SNS
In this repository, we will explore how to automate image resizing using AWS S3, Lambda, and SNS, enabling efficient image management and delivery.

![alt text](architecture.gif)


## Introduction:

In today’s digital age, images play a crucial role in various applications and websites. However, managing and serving images of different sizes can be a challenging task. To overcome this challenge, we can leverage the power of cloud computing and automation to resize images on-the-fly.

let’s dive into the implementation details and automate the image resizing process step by step. By the end of this blog post, you will have a fully functional system that can automatically resize images and store them in a separate bucket, while notifying a subscribed email address about the successful resizing process.

## Let’s get started!

In this project, we will be creating `two buckets`. The first bucket will be used to store the `original images` that we want to resize. The second bucket will be dedicated to storing the `resized images`. The resizing process will be automated through an `AWS Lambda function`, which will automatically upload the resized images to the `second bucket.`


### 1. Enter the name of `Bucket1` and click on `Create bucket.`
![alt text](bucket1.png)


### 2. Enter the name of `Bucket2` and click on `Create bucket.`
![alt text](bucket2.png)


### 3. Now, let’s create an `SNS topic` and an `SNS subscription` before creating a `lambda function.` First click on Create topic. Select Standard type SNS topic and enter the suitable name for your SNS topic and click on `Create topic.`

![alt text](sns-topic.png)


### 4. As you can see in the below screenshot, we have configured the SNS topic. Now, click on `Create subscription` to add your `email address.`
![alt text](subscription.png)


### 5. After creating Subscription, you will get a notification on your given mail address if not, please check your spam box. The mail will look like the below screenshot.

Click on Confirm subscription to get the notification for the resized image.
![alt text](image.png)


### 6. Once you confirm your subscription. The status should be `Confirmed` from Pending status.

Here, we configured the SNS topic and subscription.

![alt text](confirm-subscription.png)


### 7. Now, Let’s create a `Lambda function` that will help us to resize the images and store the images. Click on `Create function.` Enter the `function name`, `runtime(I am using Python 3.9)`, and `architecture`, and for role select the first option, So we can configure from our own all the access for the services and click on Create function.

![alt text](lambda-function.png)



### 8. First of all, replace the code with our code that will resize the image. Copy the code `Lambda-Code`, After replacing the code, deploy it by clicking on Deploy.

![alt text](lambda-code.png)


### 9. Now, we need to configure lots of things in the lambda function. Let’s start with `runtime settings`, that is, exactly under the code itself. `Click on Edit` Now, add the `handler name` according to your Python code name and click on Save.

My lambda function code name is `lambda-code` and handler name is `handler`. So, I have written `lambda-code.handler.`

![alt text](runtime-settings.png)

