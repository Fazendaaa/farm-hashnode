## Third-party cloud when you can have your own at home with the click of a button?

*> I am not the Marvel Cinematic Universe (MCU) but I like to work on hooks left where [the last story stopped](https://farm.hashnode.dev/how-to-distribute-code-to-run-on-different-architectures-answer-docker-buildx).*

# Who are you?

It's not my desire to get into the philosophical part of the question itself but to raise more questions about it:

- *Is your mother the person who knows you the most?*
- *Did your fifth-grade school record define your entire life from that moment?*
- *Do your Facebook page likes tell who [you are](https://www.wired.com/2015/01/facebook-personality-test/)?*

Considering that the estimates for this year were that [each person produced 1.7 MB of data per second](https://www.socialmediatoday.com/news/how-much-data-is-generated-every-minute-infographic-1/525692/) -- which would give about 42 [NES games](https://youtu.be/ZWQ0591PAxM) per second -- that's one of the reasons why claims like *data is ["21st-century oil"](https://www.wired.com/insights/2014/07/data-new-oil-digital-economy/)* have become popular.

![3867097_afec23a3ef_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594093620747/7IoaFYKHs.jpeg)

["mp_0146_027"](https://www.flickr.com/photos/43013992@N00/3867097) by [vphill](https://www.flickr.com/photos/43013992@N00) is licensed under [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/?ref=ccsearch&atype=rich)

# Do you [really] own your data?

*> Or are the data the one who owns you?*

![1191174633_0a6982b858_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594093977466/8mXungrLP.jpeg)

["Lion Cub"](https://www.flickr.com/photos/48355243@N00/1191174633) by [elmada](https://www.flickr.com/photos/48355243@N00) is licensed under [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/?ref=ccsearch&atype=rich)

Initiatives such as [GPDR](https://gdpr-info.eu/) -- and its "Brazilian version" [LGPD](http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018 /lei/L13709.htm) -- no matter how "commendable" they are, the main problem still is that even with the anonymization of data, opt-ins, and opt-outs in life, **companies can still use your data as a processing base**.

Just as envisioned by some projects, the idea of ​​companies paying for processing your data is becoming mainstream in some circles, maybe you even heard of [Brave](https://brave.com/). Or even as MKBHD put it once in an [interview with Joe Rogan](https://youtu.be/QSGaMUBC4Mc) that if Google is to have the data from him that at least gave benefits back, like information to leave home early to go to work because of traffic.

As Richard Stallman has pointed out over and over again, the idea of ​​"practicality" can be a cover to put you in handcuffs since many of this software go beyond the idea of ​​*vendor lock-in* and reach the point of being a crime. In some countries, the distribution of software that breaks down the security of systems to take a look at the core of the application or even the hardware can be considered a crime.

# NextCloud

![3799007336_6b7ffa4cbc_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594094556842/Cz6z-1Qfb.jpeg)

 ["Ditto"](https://www.flickr.com/photos/32224133@N07/3799007336) by [sickmouthy](https://www.flickr.com/photos/32224133@N07) is licensed under [CC BY-NC 2.0](https://creativecommons.org/licenses/by-nc/2.0/?ref=ccsearch&atype=rich)

The main point of this text is not to present [NextCloud](https://nextcloud.com/) as a "product" but to comment on how it can help you have greater control over your data and be one of the options for you. If you don't like their proposal, some competitors will be linked in the "going further" at the end of this text.

## Rancher

If you have an instance of [Rancher](https://rancher.com/) already running in your home or even a simple Single Board Computer (SBC) leftover in some corner you can use the [official image](https://hub.docker.com/_/nextcloud/) of the project and run it with a terminal command, or even simply through the clicks of a button. It is just **ONE** image and not several that could be orchestrated in a `docker-compose.yml`.

Here is how it got on my cluster [previously configured](https://farm.hashnode.dev/rancher-arm):

![image887.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594169734033/ITsHHtWxp.png)

![image875.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594169754871/ivCa2GaiO.png)

Right after that just press the "Launch" button and access the service on the door that you have allocated to it - in my case the `8888`:

![g875.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594169990033/w1U3nv7lx.png)

*note: I ended up creating a folder on the server to store the data generated on the host, however, I highly recommend you to check which of the storage solutions better suits your needs*

# It's your decision

![4739085405_22c4325a22_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594094370229/VJEDibzzq.jpeg)

["Bif. & Gare de St Vaast Bosville - 088"](https://www.flickr.com/photos/44007425@N05/4739085405) by [8Uhr](https://www.flickr.com/photos/ 44007425 @ N05) is licensed under [CC BY-NC 2](https://creativecommons.org/licenses/by-nc/2.0/?ref=ccsearch&atype=rich)

If you decide to follow the path of deploying your own NextCloud instance, first of all, consider the points presented in the next topics.

## Everything in one place is not necessarily the best idea

Please follow the *3-2-1 rule* for backups:

- 3 copies of data
- 2 stored on different media
- 1 located outside

The most recommended would be, even before running NextCloud "in production" at your home, for you to consider only make tests with it either at home or even in some cloud provider like [Linode](https://www.linode.com/); if you don't have the hardware to run at home 24/7 yet, maybe take a look at some Network Attached System (NAS) pre-builts or even try it to make your own.

## Access away from home

Remembering that if you wanted to access your new cloud you will need a static IP and coincidentally two days ago a co-worker and I did this, through [noip](https://www.noip.com/) with the help of [this](https://github.com/coppit/docker-no-ip) Docker that is also running on the same Rancher server as the company.

note: in our case we are also using OpenVPN on a Netgate running [pfSense](pfsense.org/), which I intend to write about it later on

## Overhead

*> Yes, you will have to adapt ...*

Years and years using the services of Microsoft, Google, Apple, or even -- if you are like my father -- BOL, can become a big headache at first, but it might be worth it for you.

# Going beyond

![5246212149_f4f6d468f2_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594094688376/bHAC6Xg5x.jpeg)

 ["Rocky Statue"](https://www.flickr.com/photos/56861532@N06/5246212149) by [toriecarr822](https://www.flickr.com/photos/56861532@N06) is licensed under [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/?ref=ccsearch&atype=rich)

- Publication cover photo: [".sun."](Https://www.flickr.com/photos/8276992@N06/3334118634) by [amish.patel](https://www.flickr.com/ photos / 8276992 @ N06) is licensed under [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/?ref=ccsearch&atype=rich)
- [Facebook manipulated 689003 users emotions for science](https://www.forbes.com/sites/kashmirhill/2014/06/28/facebook-manipulated-689003-users-emotions-for-science/)
- [Illegal prime](https://en.wikipedia.org/wiki/Illegal_prime)
- [DeCSS](https://en.wikipedia.org/wiki/DeCSS)
- [NextCloud vs ownCloud](https://civihosting.com/blog/nextcloud-vs-owncloud/)
- [seafile](https://www.seafile.com/en/home/)
- [Build a Raspberry Pi NAS with 4 Hard Drives and RAID](https://youtu.be/O-FfOWdZAQ4)
- [RAID is Not a Backup Solution](https://www.2brightsparks.com/resources/articles/RAID-is-not-a-backup-solution.html)
- [Netshoes pays R $ 500 thousand in moral damages after data leakage](https://tecnoblog.net/277594/netshoes-acordo-mpdft-vazamento-dados/)
- [Institute notifies Dataprev and indicates leakage of INSS data](https://idec.org.br/idec-na-imprensa/instituto-notifica-dataprev-e-aponta-vazamento-de-dados-do-inss)