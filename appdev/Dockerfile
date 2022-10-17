FROM ubuntu:latest

RUN apt-get update -y 
RUN apt-get upgrade -y
RUN apt-get install -y --no-install-recommends \
  git \
  wget \
  curl \
  zip \
  unzip \
  apt-transport-https \
  ca-certificates \
  gnupg  

# download Flutter SDK from Flutter Github repo
RUN git clone https://github.com/flutter/flutter.git /usr/local/flutter

# Set flutter environment path
ENV PATH="/usr/local/flutter/bin:/usr/local/flutter/bin/cache/dart-sdk/bin:${PATH}"

# Run flutter doctor
RUN flutter doctor

# Copy files to container and build
WORKDIR /usr/presentation/
COPY ./presentation/ . 

RUN flutter --build-dir=public

# Record the exposed port
EXPOSE 5000

CMD ["flutter", "run", "-d", "web-server"]