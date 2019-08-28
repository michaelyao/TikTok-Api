# Unoffical TikTok API in Python

This is an unoffical api wrapper for tiktok.com in python. With this api you are able to call most trending and fetch specific user information.

## Important Information
* If this API stops working for any reason open an issue.
* Feel free to mention @davidteather in an issue you open, because I might not see it otherwise.

## Getting Started

To get started using this api follow the instructions below.

It is quite a long installation process just for a TikTok api, the first release can be found [here](https://github.com/davidteather/TikTok-Api/releases/edit/v1.0) and is not as suitable for long term projects, however it may be easier for a day of scraping TikTok, as the installation is much easier.

Despite this, I **still recommend** you follow this process and use the latest version.

### Installing

If you need help installing or run into some error, please open an issue. I will try to help out as much as I can.

Tested with python 3.7.3

```
pip install requests
pip install selenium
pip install browsermob-proxy
pip install psutil
```

* You do need to have **java installed**.
* You must add **browsermob-proxy/bin** to your environment path.
* This library uses Browsermob-proxy, they are licensed under the apache2.0 license. Please make sure you adhere to their guidelines in /browsermob-proxy/LICENSE.txt
* **Firefox** must be installed.
* You must download the latest **geckodriver** from [mozilla](https://github.com/mozilla/geckodriver/releases), and include the .exe in your path.

Include whatever python script you want to run in the same directory as tiktok.py. Or just change the getTrending.py.

I will be looking for ways to shorten this installation in the future as it's a lot just for a TikTok API, however it does work 100% of the time after generating a new signature automatically.

## Quick Start Guide

Here's a quick bit of code to get the most recent trending on TikTok

```
from tiktok import TikTokapi

api = TikTokapi()

# Will Get the 10 most recent trending on the tiktok trending page
api.trending(10)
```

## Detailed Documentation

### The TikTok class

```
# Variable set like
api = TikTokapi()
```

The program will then verify a signature by opening firefox tab and checking the network packets.

##### The Trending Method

```
# Where count is how many result you want
# Verbose is optional, default=0. Set it to 1 to get more information
api.trending(count, verbose)
```

Trending returns an array of json objects. Example structure [here](https://gist.github.com/davidteather/0be2e495e2de54098e8f2a9594581d27)
JSON object tree [here](https://gist.github.com/davidteather/bc4baef0edb621dd322c8ad128a31ac1)

##### The userPosts Method

```
# Where count is how many results you want
# Verbose is optional, default=0. Set it to 1 to get more information
# userid is the tiktok userid, can be found through response json tree or in the tiktok url
api.userPosts(userid, count, verbose)
```

Since this isn't an offical TikTok API the TikTok servers don't know what to do. This method specifically will throw a lot of errors if you have verbose on. It takes a lot longer than trending, however it will still end up working. Just give it a few minutes.

Trending returns an array of json objects. Example structure [here](https://gist.github.com/davidteather/a5c1e54de353353f77a78139d2e5a9f9)
It has the same JSON object tree as trending. It's [here](https://gist.github.com/davidteather/bc4baef0edb621dd322c8ad128a31ac1) anyways.

## Built With

* [Python 3.7](https://www.python.org/) - The web framework used

## Authors

* **David Teather** - *Initial work* - [davidteather](https://github.com/davidteather)

See also the list of [contributors](https://github.com/davidteather/TikTok-Api/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details