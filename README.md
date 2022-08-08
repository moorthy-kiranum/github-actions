## Guide to Build and Deploy Applications in AWS EBS using Github Actions

1. Create a EC2 Instance from [here](https://aws.amazon.com/ec2/)  
    - ##### To Connect EC2 instance :
                1. Click on Connect button near launch instance
                2. Use any of the 3 options to connect your instance (browser-based ssh connection is pretty much easier than others)
        
3. Navigate to your working repository and Create a self hosted runner from  Settings -> Actions -> Runners
    - Select the environment where the runner is going to be install (select similar to EC2 instance Environment)
    - Select the architecture
    - Run all the commands shown in your EC2 instance created from #1

4. Create a S3 bucket from [here](https://docs.aws.amazon.com/AmazonS3/latest/userguide/creating-bucket.html) and enable public access for the bucket
5. Create a ElasticBeanStalk Application from [here](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.environments.html) 
6. Create a IAM user for programmatic access from [here](https://us-east-1.console.aws.amazon.com/iamv2/home#/home) and make sure whether it has all the below access:
    - AWSS3FullAccess
    - AWSEC2FullAccess
    - AWSCloudfromationFullAccess
    - AdministratorAccess-AWSElasticBeanstalk </br>
      `These are predefined policies provided by AWS . We can also create our own policies based on the requirement`</br>
7. Once you done with creating IAM user you will get a ACCESS_KEY_ID and ACCESS_KEY (please store the `access_key` somewhere. you can't see the same access_key value again)

8. Create a directory named `workflows` inside `.github` directory in root folder.</br>
    Looks Like
    ```
        ├── .github 
        │   ├── workflows 
        │   │   ├── *.yaml // here goes all the github-action files 
        ├── build 
        ├── src 
    ```
     `To know more about github actions [Click Here](https://docs.github.com/en/actions/quickstart)`

 - `Note: make sure all the above aws components are created in same region`
