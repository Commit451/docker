FROM java:openjdk-8-jdk
# Install Ruby
RUN cd
    git clone https://github.com/rbenv/rbenv.git ~/.rbenv
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(rbenv init -)"' >> ~/.bashrc
    exec $SHELL
    git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
    echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
    exec $SHELL
    rbenv install 2.4.0
    rbenv global 2.4.0
    ruby -v
    gem install bundler
# Installs Android SDK
RUN gem install android-sdk-installer
    android-sdk-installer
