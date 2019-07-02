FROM softinstigate/serverless

WORKDIR /

RUN apt-get install -y libreadline-gplv2-dev \
		libncursesw5-dev \
		libssl-dev \
		libsqlite3-dev \
		tk-dev \
		libgdbm-dev \
		libc6-dev \
		libbz2-dev \
		tree && \
	wget https://www.python.org/ftp/python/3.6.8/Python-3.6.8.tgz && \
	tar xvf Python-3.6.8.tgz && \
	cd Python-3.6.8 && \
	./configure && \
	make && \
	make install

RUN pip3 install virtualenv

WORKDIR /ServerlessSpace