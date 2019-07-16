FROM amazonlinux:1

WORKDIR /

RUN yum update -y && \
	yum install -y python36 && \
	curl -O https://bootstrap.pypa.io/get-pip.py && \
	python3 get-pip.py && \
	rm get-pip.py

RUN curl -sL https://rpm.nodesource.com/setup_12.x | bash - && \
	yum install -y nodejs && \
	npm install -g serverless

ADD ./requirements.txt /requirements.txt

RUN pip install -r requirements.txt

WORKDIR /ServerlessSpace