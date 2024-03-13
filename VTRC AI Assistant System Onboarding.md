# VTRC AI Assistant System Onboarding

## Getting an Instance [AWS]

As for the region of aws: `us-east-1` and `us-west-2` could be cheaper.

The first step is to start up an EC2 instance with the appropriate resources. We recommend at least 16GB of RAM, 4-8vCPU cores, and 300GB of disk for a small-mid sized organization (< 5000 users). For reference, in our Cloud offering we use a `m7g.xlarge` with 500GB of EBS storage.

![Instance](https://mintlify.s3-us-west-1.amazonaws.com/danswer/images/setup_guides/aws/Instance.png)

When setting up the security group for the new instance, make sure that you allow for HTTPS and HTTP traffic.

![Instance](https://mintlify.s3-us-west-1.amazonaws.com/danswer/images/setup_guides/aws/InstanceNetworking.png)

## Installing Dependencies

```
sudo yum update -y

sudo yum install docker -y
sudo service docker start

sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

sudo yum install git
```

## Starting up Danswer

```
git clone git@github.com:FangxuY/chatbox.git

cd danswer/deployment/docker_compose

sudo docker-compose -f docker-compose.dev.yml -p danswer-stack up -d --build --force-recreate 
(It may cost 15+ mins for the first time created)

```

![image-20240313104429518](/Users/yuanfangxu/Library/Application Support/typora-user-images/image-20240313104429518.png)

After all Container started, you could visit the console.

For console url, you could find it on your EC2 Dashboard

![image-20240313104704233](/Users/yuanfangxu/Library/Application Support/typora-user-images/image-20240313104704233.png)