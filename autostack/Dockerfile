## BUILDING
##   (from project root directory)
##   $ docker build -t php-for-scottiems-crm-limai .
##
## RUNNING
##   $ docker run -p 9000:9000 php-for-scottiems-crm-limai
##
## CONNECTING
##   Lookup the IP of your active docker host using:
##     $ docker-machine ip $(docker-machine active)
##   Connect to the container at DOCKER_IP:9000
##     replacing DOCKER_IP for the IP of your active docker host

FROM gcr.io/stacksmith-images/minideb-buildpack:jessie-r8

MAINTAINER Bitnami <containers@bitnami.com>

ENV STACKSMITH_STACK_ID="glvpc28" \
    STACKSMITH_STACK_NAME="PHP for scottiems/crm-limai" \
    STACKSMITH_STACK_PRIVATE="1"

# Install required system packages
RUN install_packages libc6 zlib1g libxslt1.1 libtidy-0.99-0 libreadline6 libncurses5 libtinfo5 libsybdb5 libmcrypt4 libldap-2.4-2 libstdc++6 libgmp10 libpng12-0 libjpeg62-turbo libbz2-1.0 libxml2 libssl1.0.0 libcurl3 libfreetype6 libicu52 libgcc1 libgcrypt20 libgssapi-krb5-2 libgnutls-deb0-28 libsasl2-2 liblzma5 libidn11 librtmp1 libssh2-1 libkrb5-3 libk5crypto3 libcomerr2 libgpg-error0 libkrb5support0 libkeyutils1 libp11-kit0 libtasn1-6 libnettle4 libhogweed2 libffi6

RUN bitnami-pkg install php-7.1.0-1 --checksum 069f80b98b29998601f10685462b2f499cd95c5c56d036b4a3d2b5f64d310028

ENV PATH=/opt/bitnami/php/bin:$PATH

## STACKSMITH-END: Modifications below this line will be unchanged when regenerating

# PHP base template
COPY . /app
WORKDIR /app

CMD ["php", "-a"]
