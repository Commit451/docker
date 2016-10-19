FROM java:openjdk-8-jdk
ENV ANDROID_SDK_VERSION r24.4.1
ENV ANDROID_BUILD_TOOLS_VERSION 24.0.3
ENV ANDROID_API_LEVELS android-24
ENV ANDROID_LICENSES android-sdk-license-5be876d5|android-sdk-license-c81a61d9
# Installs i386 architecture required for running 32 bit Android tools
RUN dpkg --add-architecture i386 && \
    apt-get update -y && \
    apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 expect && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get autoremove -y && \
    apt-get clean
# Installs Android SDK
ENV ANDROID_HOME /opt/android-sdk-linux
ENV ANDROID_SDK_FILENAME android-sdk_${ANDROID_SDK_VERSION}-linux.tgz
ENV ANDROID_SDK_URL http://dl.google.com/android/${ANDROID_SDK_FILENAME}
ENV ACCEPT_LICENSES_FILENAME accept-licenses
ENV ACCEPT_LICENSES_URL https://raw.githubusercontent.com/journeyapps/android-sdk-installer/master/${ACCEPT_LICENSES_FILENAME}
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
RUN cd /opt && \
    wget -q ${ANDROID_SDK_URL} && \
    tar -xzf ${ANDROID_SDK_FILENAME} && \
    rm ${ANDROID_SDK_FILENAME} && \
    wget -q ${ACCEPT_LICENSES_URL} && \
    chmod +x ${ACCEPT_LICENSES_FILENAME} && \
    ./${ACCEPT_LICENSES_FILENAME} "android update sdk --no-ui -a --filter tools,platform-tools,${ANDROID_API_LEVELS},build-tools-${ANDROID_BUILD_TOOLS_VERSION},extra-android-m2repository" "${ANDROID_LICENSES}" && \
    rm ${ACCEPT_LICENSES_FILENAME}
