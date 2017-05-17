FROM java:openjdk-8-jdk
# Install Ruby http://stackoverflow.com/a/33064386/895797
RUN cd
RUN sudo apt-add-repository ppa:brightbox/ruby-ng
RUN sudo apt-get update
RUN sudo apt-get install ruby2.4
# Installs Android SDK
RUN gem install android-sdk-installer
RUN android-sdk-installer
