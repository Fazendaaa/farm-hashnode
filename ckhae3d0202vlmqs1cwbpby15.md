## Data analysis website ... But it's actually an app on Android, Windows, Mac, and your iPhone

> First of all: "I miss Windows Phone"

cover photo: ["Beijing Apple Store"](https://www.flickr.com/photos/22795534@N00/2680396716) by [guanmu.name](https://www.flickr.com/photos/22795534 @ N00) is licensed under [CC BY-NC-ND 2.0](https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=rich)

# Intro

Continuing from where the [last post](https://farm.hashnode.dev/data-analysis-website-database-all-this-on-your-pc-and-without-having-to-install-r-shiny-and-mongo) stopped: the possibility of transforming a data analysis website made with R and Shiny into a mobile app. However, the mentioned package had an interface with little flexibility, heavy, and that presented a low Return of Investment (ROI). So I decided to [make one](https://github.com/Fazendaaa/shinyPWA) that better met my needs.

![38758228251_007e6a0f00_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594618695900/ZLwLmVUzI.jpeg)

["IMG_0769"](https://www.flickr.com/photos/25612179@N00/38758228251) by [Miranda Jan](https://www.flickr.com/photos/25612179@N00) is licensed under [CC BY-NC-ND 2.0](https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=rich)

# Progressive Web Apps (PWAs)

## What are they?

A PWA is when the website and the browser can interpret the website kinda like a native app. That means everything running in a browser overnight could be turned into an app using the browser as your store.

You won't have to worry about several languages ​​like Kotlin, Swift, Objective C, Java, C #, etc. Besides the overhead of requiring labor that is often more expensive, they also require having to pay a developer account to publish on the platforms they want, which ends up making the product even more expensive.

You make your website the way you feel most comfortable with -- what money/time allows -- and you will have to add two more files basically:

1. A browser compatibility checker -- basically JavaScript that will see if the browser the user is running on is compatible to be used as a store; in the example to be shown the checker doesn't reach 15 lines of code
2. A manifest -- `manifest.json` -- which contains information about your website such as name, color, icons, etc.

It may seem simple and a spoiler: "it is". And, as you can see, the last project has become one without any overhead:

![PWA](https://media1.tenor.com/images/7247ed61cdad62f640f05fc08a56d607/tenor.gif?itemid=17780575)

note: I know that a PWA has **A LOT** more involved in it, but this is the bulk of it. The other steps, such as communication, push notification, access to cell phone data, etc., could be implemented but would be too much to point out in this text, my main concern is to show the basic idea.

## Story

PWAs, according to some in the community, was an idea [envisioned by Steve Jobs](https://medium.com/progressivewebapps/history-of-progressive-web-apps-4c912533a531) when the first iPhone launched because the App Store did not exist then.

A curious fact is to think that last year [**519 BILLION DOLLARS **](https://www.theverge.com/2020/6/15/21292203/apple-app-store-ios-apps-billings-revenue-517-billion-2019-antitrust-regulation) flow through the App Store. Apple took a generous 30% share of this; that is, *measly* $155 billion.

![353368957_465a5ede81_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594608726459/TyPo8N2ug.jpeg)

["iPhone"](https://www.flickr.com/photos/77526889@N00/353368957) by [Reder](https://www.flickr.com/photos/77526889@N00) is licensed under [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/?ref=ccsearch&atype=rich)

RSMD running as an app on Mac:

![photo_2020-07-13_01-41-45.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594615411339/Rd9zL612l.jpeg)

## Important points

PWAs have the option of being accessed by all supported browsers and added as an app. Some sites that are already PWAs -- such as Twitter, Starbucks, Telegram, Tinder, Uber, etc. -- already ask you if you want to add them to your mobile phone when you access it:

![untitled-f000277.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594610213435/97Ntkpzih.png)

The idea of ​​having an icon and being accessible directly from your home screen or even from your Windows search bar is that your website is a first-class citizen wherever you are.

![untitled-f000408.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594610260360/klMSB8KP8.png)

The loading screen is another important factor, as it will try to load all the resources while the user waits.

![untitled-f000438.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594610270333/HQItvbqyA.png)

They also have their window in the app manager, be it on your phone or the  *multi-task view* on your computer.

![untitled-f000597.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1594610305505/nET0D3iQ0.png)

note: this is Samsung's browser, but it works on the latest Chrome for Androids as well - and I did tests with Edge without any major headaches.

## I am not a dev: why should I care?

If you think that what has been pointed out so far is too much of a mambo-Jambo for your taste, just that a look at this:

1. **Low cost**: no longer having to worry about making 500 Android apps -- due to market segmentation and system versions --, iOS, Windows, Mac, etc. Just do **ONE** website -- not that it will make a difference in market share: *"also runs on Linux and FreeBSD too"*
2. **Time to market (TTM)**: if you have set up Continuous Integration (CI) and Continuous Delivery (CD) when you save a code to your favorite Git provider, then in a few moments later you will have updated it for all of your customers, without needing anyone to *put into production*
3. **Don't break the web**: this is one of the oldest mottos in web development, shows the concern of web developers to build a service that works for years to come and be retro compatible.

![405498965_b1d9c68fc1_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594618977569/xsx3FF8j3.jpeg)

["exponential"](https://www.flickr.com/photos/44124366475@N01/405498965) by [topgold](https://www.flickr.com/photos/44124366475@N01) is licensed under [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/?ref=ccsearch&atype=rich)

I only brought three points to avoid having a text wall here in the text, but if you want to chat on [Twitter](https://twitter.com/the_fznd), I will be more than happy to mention more -- besides recommending looking at the references in this post.

## I'm a dev, but I still don't see any advantages

> Take your time, think again

Some of the benefits of worrying about PWA development right now:

- If you already have a website running, you won't have to try to port to one in the future and have to worry about more variables and to train the team to know all this at the last minute
- Allows you to feel the site as an app right now on your phone, just like I did.  The advantage of this approach is not run an emulator on your PC or a tool like `Lighthouse` -- *which, although very good for [80% of cases, will always have that 20%](https://en.wikipedia.org/wiki/Pareto_principle) that you won't be able to provide a real use case*
- Expanding knowledge of new technology. Even if you don’t end up liking it or you don’t feel it is the best thing for you -- *as the next topic will show, the initial effort is almost zero*

![8254585607_200890d709_o.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1594619084024/AZApP3ij_.jpeg)

["Glasgow, Scotland"](https://www.flickr.com/photos/80018584@N06/8254585607) by [Seo J Kim](https://www.flickr.com/photos/80018584@N06) is licensed under [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/?ref=ccsearch&atype=rich)

# Why still on Shiny?

> Why not?

I said that `Shiny` has many cons, that doesn’t change the fact that the platform is still VERY used, It's the most used web framework for anyone using R. And you can have all of this by making a call of approximately ten lines of code:

```R
...
    dashboardBody (
        shinyPWA (list (
            hasIcons = TRUE,
            version = 'v1',
            shortname = 'RSMD',
            name = 'R + Shiy + Mongo + Docker',
            display = 'standalone',
            backgroundcolor = '#fdfdfd',
            themecolor = '# db4938',
            orientation = 'portrait-primary'
        )),
...
```

Important to point out that even as the example shows `shinyDashboard` used but it is not necessary; only `shiny` itself is required. If some optimization is made here and there, neither would it be necessary, but as the idea is to use it in a project that already runs `shiny`.

I do not see the need for such optimization to be able to port to another competitor that does not exist.

# Running location

> Time has come for the "Docker Witness" to shine

If you have already downloaded the project, open your terminal and run:

```shell
docker-compose up
```

Now access your machine's IP from any of your devices on the local ethernet, or just open your browser on your machine and type `localhost`.

# Publishing

As I said before: some of the app stores already allow you to post PWAs on it and can end up giving your system greater visibility. And you won't have to worry about building anything to distribute since it is a website, nothing to worry about a complex and elaborate production pipe.

# References

- [Microsoft and Google team up to make PWAs better in the Play Store](https://medium.com/pwabuilder/microsoft-and-google-team-up-to-make-pwas-better-in-the-play-store-b59710e487)
- [10 Reasons Why Your Business Needs a Progressive Web App](https://www.sam-solutions.com/blog/the-benefits-of-progressive-web-apps-pwa-for-business/)
- [PWA Group](https://t.me/pwabrasil)
- [PWA starter kit: build fast, scalable, modern apps with Web Components (Google I/O '18)](https://youtu.be/we3lLo-UFtk)
- [How to publish a PWA on the Google Play store](https://dev.to/jumpalottahigh/how-to-publish-a-pwa-on-the-google-play-store-2bid)
- [Progressive Web Applications](https://developer.microsoft.com/pt-br/windows/pwa/)
- [Why Build Progressive Web Apps: PWAs for iOS](https://www.youtube.com/watch?v=s5ASNwnBttQ)