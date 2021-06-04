# Stateful_Information
## Install
This project requires [spark](https://www.apache.org/dyn/closer.lua/spark/spark-3.1.2/spark-3.1.2-bin-hadoop3.2.tgz) and [netcat](https://nmap.org/ncat/)

## Background
Here we are going to use an example of actually maintaining state across sessions in a weblog.
So if you need to maintain some sort of state while data streaming in, maybe you're keeping some running totals or in our example, we're going to be maintaining the state of a session as a individual IP clicks through a Web site, you can do that with smart streaming.
You don't have to just discard the data as soon as you get it or write it out or whatever you want to do.
You can actually keep track of stuff as you go and that's what Map with State does.

## Code
Template code files are `Sessionizer.scala` and `Utilities.scala`. `access_log_sample_git.txt` contains sample log informations from a website. 

## Run
For running this example you can use an IDE like [scala IDE](http://scala-ide.org/download/sdk.html). Open a terminal and run netcat with

> ncat -kl 9999 < access_log_sample_git.txt

and after that you run the spark code using IDE. In console of the IDE you will get the real time session output.

## Sample Output
 ip | sessionLength| clickstream
 ---: | ---: | ---:
 195.154.250.88|         1724| /?feed=rss2, /fe...
 66.249.75.168|            2|/blog/, /nationa...
   142.4.4.201|            1|     /wp-login.php
  180.76.15.33|            2|              /, /
 91.217.232.65|            1|     /wp-login.php
 192.99.10.173|            1|                 /
 211.23.70.202|            1|     /wp-login.php
 180.76.15.143|            1|                 /
173.236.54.162|            3|/wp-login.php, /...
 95.154.250.29|            2|/wp-login.php, /...
  180.76.15.19|            3|           /, /, /
 184.154.124.2|            1|     /wp-login.php
144.76.218.241|            1|     /wp-login.php
   180.76.15.8|            1|                 /
 180.76.15.154|            2|              /, /
217.27.240.125|           11|/wp-login.php, /...




