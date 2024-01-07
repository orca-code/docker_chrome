FROM --platform=linux/amd64 python:3.11

# install google chrome
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
RUN apt -y update
RUN apt install -y google-chrome-stable

# set display port to avoid crash
ENV DISPLAY=:99

# innstall selenium
COPY requirements.txt /tmp/
RUN pip install -r /tmp/requirements.txt --no-cache-dir