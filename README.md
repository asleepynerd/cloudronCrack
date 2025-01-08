# cloudronCrack 🚀

> Get free infinite apps on Cloudron!

## 🔧 Installation

### Option 1: One-Line Install

```bash
curl -sL https://woah.pw/install | sudo bash -
```

### Option 2: Manual Install

1. Clone the repository

```bash
git clone https://github.com/asleepynerd/cloudronCrack.git
```

2. Give the script executable permissions

```bash
chmod +x cloudronCrack/install
```

3. Run the script

```bash
sudo ./cloudronCrack/install
```

### Why i did this

It's simple, Cloudron is overpriced, and paywalling open source software. Charging 30€ per MONTH to installed more than 2 docker containers is 100% a scam, however, yes it comes with support benefits, but there are things like forums for that.

### How?

I orginally started inspecting web requests, seeing how they were made, and then it lead to their official api which determined whether you could have it or not. So to begin with, I overwrote the api it was requesting, with my own, to always allow new apps.

However, while doing some inspecting last night, it turns out, it was much, much simpler than that. I had to comment out, 1 line. 1 singular line. You'd think someone who charges 30 quid per month would at least have some sense of security, right?

It was in the box/src/apps.js file, in the yellowtent user thats created when cloudron is installed. the line `await purchaseApp()...`, is the only thing that stood between the app installation, and the lookup of the app. all it does is make a request to the cloudron api. theres no callbacks, nothing, it just fails the request if its not valid. So commenting out, just works!

<br>

## Support

If you found this useful, please consider:

- Starring the repository: [cloudronCrack](https://github.com/asleepynerd/cloudronCrack)
- Following me on GitHub: [asleepynerd](https://github.com/asleepynerd)

If you have any issues, feel free to open an [issue](https://github.com/asleepynerd/cloudronCrack/issues/new/choose).

<br>
Links:
- Wanna see more stupid shit? Head here: [sleepy.engineer](https://sleepy.engineer)
- The github repo: [cloudronCrack](https://github.com/asleepynerd/cloudronCrack)
