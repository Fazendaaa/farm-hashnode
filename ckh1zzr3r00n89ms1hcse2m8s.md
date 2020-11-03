## Data analysis + WebSite + Database? All this on your PC and without having to install R, Shiny and Mongo

> Another text of mine ... You already know that I'll find a reason to talk about Docker

cover photo: ["Growth - Earnings Growth - Growth Sign"](https://www.flickr.com/photos/141574894@N07/27448741372) by [gfdnova1](https://www.flickr.com/photos /141574894@N07) is licensed under [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/?ref=ccsearch&atype=rich)

# Intro

I've been quoting Docker here and there for a while now, just using it without building anything. Now things start to change; I want to show you how to do data analysis using [R](https://www.r-project.org/) -- a programming language aimed at the statistical public -- with a web interface and save it to a database.

The idea is to show that even if you are on Windows, Mac, or Linux, you will be able to write a robust application that does the analysis you want and make it run wherever you want. That is, if you are on Windows, it will run on Mac and Linux -- the latter is important because if you desire to deploy it your service in the cloud, especially if you don't want to use [shinyapps.io](https://www.shinyapps.io/).

And if you want some jargon like:

- Microservices
- System As A Service
- Cloud-native
- etc.

You can guarantee that your [cargo cult](https://en.wikipedia.org/wiki/Cargo_cult), you can keep repeating them without understanding a shi#$ of what they mean.

![2097014897_aa2641d70f_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594345128529/Kk_1TPPtm.jpeg)

["Temple Curch"](https://www.flickr.com/photos/87863966@N00/2097014897) by [buggolo](https://www.flickr.com/photos/87863966@N00) is licensed under [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/?ref=ccsearch&atype=rich)

# Why R + Shiny?

> "Elementary, my dear Watson ..."

Recent graduates, researchers, and interns in the company that I work for have been exposed to R during graduation -- be it in a class, Scientific Initiation, or on their own.

However, the post is not an endorsement of using R or even Shiny -- not least because I have some points against the combination that I intend to explore in a more future text.

# "Talk is cheap, show me the code"

> Quote from Linus -- Torvalds not Sebastian

![48659436006_616e00e4f1_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594341311630/WfkjPnRsj.jpeg)

["do we write code"](https://www.flickr.com/photos/43661283@N00/48659436006) by [m.gifford](https://www.flickr.com/photos/43661283@N00) is licensed under [CC BY-NC 2.0](https://creativecommons.org/licenses/by-nc/2.0/?ref=ccsearch&atype=rich)

If you just desire to see the final product, have `docker` and` docker-compose` installed on your machine -- if you are on Windows or Mac, both are an installation only within [Docker Desktop](https://www.docker.com/products/docker-desktop).

1. Clone or download [this](https://github.com/Fazendaaa/RSMD) repository on your machine:
```shell
git clone https://github.com/Fazendaaa/RSMD
cd RSMD/
```
2. Once inside it, just run:
```shell
docker-compose up
```
3. Open your browser and type `localhost` and watch the magic happen:

![2020-07-10-021116_1259x1030_scrot.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594358348260/fP3vHcaJE.png)

The database stores all the values ​​of the number of breaks used to make the data analysis. Acting like a kind of system log, also called **audit trail** by some.

![2020-07-10-021120_1259x1030_scrot.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594358369528/8F7BJ8W5G.png)

If you are running all this on a wi-fi network, after discovering your machine's IP, you can also access the site from your mobile phone:

![image1197.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594365899062/ybyb_2kw1.png)

![image1185.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594365933933/RVV4aZeor.png)

The important thing about this visualization on your mobile phone is if you want to publish your website later on as an "app" for:

- [Google Store](https://medium.com/@firt/google-play-store- now-open-for-progressive-web-apps-ec6f3c6ff3cc)
- [Windows Store](https://docs.microsoft.com/en-us/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)
- Or even as [app on your iOS device](https://love2dev.com/pwa/ios/)
- etc.

You should take a look at [this one](https://cran.r-project.org/web/packages/shinyMobile/readme/README.html) Shiny package for Progressive Web Apps (PWA).

The scenario mentioned earlier proves to be a clear positive point for the business and the product itself. As a developer, have the assurance that everything I do will run on the client system or the cloud server -- since ** I don't have R installed on my machine ** and I only develop using containers -- it's something that:

- Avoids reworking because the product I deliver already contains ** EVERYTHING ** needed to run - no headaches lost due to the lack of an R package, or even running it in the wrong version, or even for the lack of a system library
- It gives you the security of being able to change hardware without wasting time on configurations
- "Binaries" of applications anywhere, thanks to [Docker Hub](https://hub.docker.com/). And this is because the build that I perform on my machine becomes available to everyone on my team regardless of which architecture and which system they choose to develop on it

## Important points

![30465669870_5cabb7b70b_o (1) .jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594343620118/kyi4ujIsB.jpeg)

["Robot Warning"](https://www.flickr.com/photos/37996646802@N01/30465669870) by [cogdogblog](https://www.flickr.com/photos/37996646802@N01) is licensed under [CC0 1.0](Link)

In the project's `README.md` it is highlighted how to make [Mongo](https://www.mongodb.com/) change the current behavior since the way it was configured with a 'recent memory loss'; this means that every execution it runs with a clean database. However, you can change this by adding it **one line**.

The `docker-compose` approach has its advantages:

1. Avoids that the database from being installed on the developer's machine
2. Prevents a high internet consumption because you are not using a cloud-like DB like [Atlas DB](https://www.mongodb.com/cloud/atlas) -- which helps mainly those who are doing remote work during the pandemic
3. Avoid the famous problem of using a single database instance -- now three can be applied: one for development, one for homologation, and one for production

Another main point is this base image is used because is maintained by a company. If you want to see what is in it to reproduce and remove the dependencies that you do not use, please feel free and go ahead.

In order not to get **TOO** out of the scope, I still intend to explain how the development flow of this stack is in the company that I work for.

## Did you think it was over?

> "You thought it wrong, sucker" - INGÁ, Rogerinho

![9795459904_d888cece01_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594343814092/3DgZhmZXT.jpeg)

["Every end is a new beginning."](https://www.flickr.com/photos/78592755@N06/9795459904) by [deeplifequotes](https://www.flickr.com/photos/78592755@N06) is licensed under [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/?ref=ccsearch&atype=rich)

The base image used in the project has some "advantages". It may have run on your laptop's x86 without a headache, but as already [pointed out previously](https://farm.hashnode.dev/how-to-distribute-code-to-run-on-different-architectures-answer-docker-buildx), Docker has different CPU architectures. Which means that you will be able to run this project on the following architectures:

- 386
- amd64
- arm/v6
- arm/v7
- arm64
- s390x
- ppc64le

If this ain't much of a difference for you, I recommend reading the references of the text quoted in the previous link.

# Do you want to run on a server at home?

![34028948085_44cf6ff191_o.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594342527645/ednbmbfGi.png)

["Orange Pi 2G-IoT"](https://www.flickr.com/photos/120586634@N05/34028948085) by [ghalfacree](https://www.flickr.com/photos/120586634@N05) is licensed under [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/?ref=ccsearch&atype=rich)

I always talk about having your own [server at home](https://farm.hashnode.dev/rancher-arm) even to be able to have [your own cloud](https://farm.hashnode.dev/third-party-cloud-when-you-can-have-your-own-at-home-with-the-click-of-a-button). If the situation does not allow you to do this because there is no old machine left at home, that's fine because you can make your system run 24/7 if you have the following items:

1. USB power supply
2. A microSD -- at least 8GB
3. A Raspberry Pi -- a [Zero W](https://www.adafruit.com/product/3400) should work

If you don't have all of it, everything should be around 30 USD if you buy it from a site like Amazon. Even if this price tag is too much for you, remember that many cloud providers have free trial plans of up to one year, and if you live in the college dorm room you can try to split with your friends -- you probably spend WELL more per month in beverages.

## Rancher

If you want to run on [Rancher](https://rancher.com/), just translate the `docker-compose.yml` containers into two deploys on your panel:

- The database:

![image1275.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594366289388/4-f1P5clr.png)

- The website:

![image1287.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594366294653/HDX7JR-3E.png)

The system now should be accessible from any device inside your network and out of your house through a Virtual Private Network (VPN).

note: in the case of Mongo you will not be able to run on all types of architecture since it only supports three currently

# Going beyond

- [Shiny Tutorial](https://bookdown.org/weicheng/shinyTutorial/)
- [PWS examples - Successful Progressive Web Apps](https://appmaker.xyz/pwa-examples-successful-progressive-web-apps/)