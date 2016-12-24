---
layout: post
title:  Setting up Bash to show forecasts on login
tags: misc
---

Having Bash show weather forecasts on login to a new interactive shell is helpful, since you probably open new shells more than you look up the day's weather so you'll always be aware of the weather now.

To do this, I use wego - a weather client for the terminal, bashrc - the bash script that is executed every time you open a new interactive shell. 

I'll outline the steps here, or you can just use the setup script that I've written below.

Process:

1. Download and install wego
  - Make sure you have Go installed on your system `sudo apt install go` or download the binaries from https://golang.org
  - Run `go get -u github.com/schachmat/wego` -- sudo might be necessary here.
  - If that fails, you probably need to setup your go environment. To do that, simply: 
  {% highlight bash %}
  mkdir $HOME/go

  export GOPATH=$HOME/go

  export PATH=$PATH:$GOROOT/bin:$GOPATH/bin

  echo "export GOPATH=$HOME/go" >> $HOME/.bashrc

  echo "export PATH=$PATH:$GOROOT/bin:$GOPATH/bin" >> $HOME/.bashrc

  {% endhighlight %}
2. Run `wego` once to generate a .wegorc config file
  - It will be generated in ~/.wegorc
3. Get a developer API key from forecast.io, and find your location's latitude and longitude coordinates
  - Open ~/.wegorc in an editor and put your API key and location coordinates in the relevant parameters.
4. Run `wego` to test
  - You should see the current weather for your location and a few days forecast.  To change the forecast amount edit the `days=` field in .wegorc.
5. Open `.bashrc` and insert the `wego` command anywhere.
  - I like to use this `echo "Today's Weather:" && wego | grep -vwE "(Weather)"` which removes the "Weather for: {coordinates}" line and inserts "Today's Weather:", it looks nicer.
6. Open a new terminal and you should see something similar to the image below

![image]({{ site.url }}/assets/img/wego.png)


Here's the setup script if you would like to skip those steps. Be warned - this is not very well tested so it might not work for everyone.

You may need to run `chmod +x setup.sh` to make it executable and you may also need to run it with sudo like so `sudo ./setup.sh YOUR_API_KEY`

<script src="https://gist.github.com/alec-chan/13c3b16d394152c0e9d864d42cd65cef.js"></script>
