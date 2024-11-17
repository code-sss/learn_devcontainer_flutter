FROM ghcr.io/cirruslabs/flutter:stable

# Install requirements for Linux desktop support
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends clang cmake ninja-build pkg-config libgtk-3-dev liblzma-dev

# Install Chrome
RUN wget -qO /etc/apt/keyrings/linux_signing_key.pub https://dl-ssl.google.com/linux/linux_signing_key.pub
RUN echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/linux_signing_key.pub] https://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y google-chrome-stable

RUN yes | sdkmanager --licenses && sdkmanager --update && sdkmanager "system-images;android-34;google_apis_playstore;x86_64" "emulator"

RUN avdmanager create avd -n android-emulator -k "system-images;android-34;google_apis_playstore;x86_64" --device "pixel"