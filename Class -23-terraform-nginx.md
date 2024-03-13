# create 2 EC2 instance on 2 different regions and install nginx using terraform script
# main.tf

provider "aws" {
  alias = "ap-south-1"
  region = "ap-south-1"
  
}

resource "aws_instance" "ec2Mumbai" {
  provider = aws.ap-south-1
  ami           = "ami-03bb6d83c60fc5f7c"
  instance_type = "t2.micro"
  key_name      = "key1"

  user_data = <<-EOF
            #!/bin/bash
            apt update -y
            apt install nginx -y
            systemctl start nginx
            EOF
  tags = {
    name = "nginx-instance"
  }
}
  provider "aws" {
  alias = "us-east-1"
  region = "us-east-1"
  
}
  resource "aws_instance" "ec2NVirginia" {
  provider = aws.us-east-1
  ami           = "ami-07d9b9ddc6cd8dd30"
  instance_type = "t2.micro"
  key_name      = "key1"

  user_data = <<-EOF
            #!/bin/bash
            apt update -y
            apt install nginx -y
            systemctl start nginx
            EOF
  tags = {
    name = "nginx-instance"
  }
}

