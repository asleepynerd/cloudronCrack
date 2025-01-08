# cloudronCrack
Get free infinite apps on cloudron !

Avalaible via:

### Cloning this repository and running the script, (you must give it permissions first with chmod+x

### 1 Line install script
```
curl -sL https://woah.pw/install | sudo bash -
```

### Why i did this

It's simple, Cloudron is overpriced, and paywalling open source software. Charging 30€ per MONTH to installed more than 2 docker containers is 100% a scam, yes it comes with support benefits, but there are things like forums for that.

### How?

I orginally started inspecting web requests, seeing how they were made, and then it lead to their official api which determined whether you could have it or not. So to begin with, I overwrote the api it was requesting, with my own, to always allow new apps.

However, while doing some inspecting last night, it turns out, it was much, much simpler than that. I had to comment out, 1 line. 1 singular line. You'd think someone who charges 30 quid per month would at least have some sense of security, right?

It was in the box/src/apps.js file, in the yellowtent user thats created when cloudron is installed. the line `await purchaseApp()...`, is the only thing that stood between the app installation, and the lookup of the app. all it does is make a request to the cloudron api. theres no callbacks, nothing, it just fails the request if its not valid. So commenting out, just, works!

for more stupid shit, you can see my main site, https://sleepy.engineer
