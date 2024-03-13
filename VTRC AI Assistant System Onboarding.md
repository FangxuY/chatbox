<img width="1428" alt="image" src="https://github.com/FangxuY/chatbox/assets/48797491/78f307aa-5fb5-4a82-912c-ce6412955e25"># VTRC AI Assistant System Onboarding

## Getting an Instance [AWS]

As for the region of aws: `us-east-1` and `us-west-2` could be cheaper.

The first step is to start up an EC2 instance with the appropriate resources. We recommend at least 16GB of RAM, 4-8vCPU cores, and 300GB of disk for a small-mid sized organization (< 5000 users). For reference, in our Cloud offering we use a `m7g.xlarge` with 500GB of EBS storage.

![image](https://github.com/FangxuY/chatbox/assets/48797491/ffa4ac46-283f-4c03-8338-a357be66b6e2)


When setting up the security group for the new instance, make sure that you allow for HTTPS and HTTP traffic.

![image](https://github.com/FangxuY/chatbox/assets/48797491/9c071c46-8bd9-4194-a21a-24af8389e19e)


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
<img width="1165" alt="image-20240313104429518" src="https://github.com/FangxuY/chatbox/assets/48797491/80d74517-bebb-495c-9767-89e637114e75">

After all Container started, you could visit the console.

## Visiting console
For console url, you could find it on your EC2 Dashboard
<img width="1129" alt="image-20240313104704233" src="https://github.com/FangxuY/chatbox/assets/48797491/96ca3952-d9d2-45ac-a0d8-92dfe75b2930">

Input the url like "http://ec2-35-175-246-19.compute-1.amazonaws.com/", you could get the VTRC AI Assistant like:
<img width="1428" alt="image" src="https://github.com/FangxuY/chatbox/assets/48797491/3d6638f2-060f-4efd-9978-ae2401af29cb">


