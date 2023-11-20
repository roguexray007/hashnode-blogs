---
title: "Mastering Log Parsing for Enhanced Productivity 🚀"
datePublished: Mon Nov 20 2023 06:19:07 GMT+0000 (Coordinated Universal Time)
cuid: clp6inuqz00010aid0nc363pi
slug: mastering-log-parsing-for-enhanced-productivity
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700461015381/54a34383-3ccb-4d9b-815f-3c03603674fc.png
tags: terminal, kubernetes, developer, debugging, logging

---

---

# Introduction

Hello, Readers! 👋 Exciting news! I’ve discovered a game-changing setup that’s supercharged my productivity. It’s all about efficiently managing raw logs, like those from Kubernetes pods. This method not only simplifies your workflow but also turns raw log data into valuable insights. It’s a must-have for anyone looking to level up their debugging game. Ready to dive in? Let’s go! 💡

## The Challenge of Log Parsing ❓

As developers, we often find ourselves grappling with the task of parsing and viewing logs on the terminal. Without color coding and formatting, it can be quite a challenge to make sense of the vast streams of data. 🔎

## My Productivity-Boosting Approach 🛠️

To tackle this challenge, I’ve experimented with a few strategies that have proven to be quite effective:

1. **Interactive Filtering with Peco**: I push logs into a file and filter them interactively later using Peco. Here’s the command I use:
    
    ```bash
    k logs <pod> > ~/Desktop/abc.json && peco ~/Desktop/abc.json
    ```
    
2. **Streaming Logs with JQ**: I stream logs from the pod to stdout and a file (for later use), and parse them using JQ. Here’s how:
    
    ```bash
    k logs -f <pod> | tee -a ~/Desktop/abc.json | jq
    ```
    
    However, JQ doesn’t work well if there are non-json objects in logs, so I created my own script:
    
    ```bash
    function kjq() {
        cut -d' ' -f4- |  jq -R '. as $line | try (fromjson) catch $line'
    }
    ```
    
    Now, I can use kjq like this:
    
    ```bash
    k logs -f <pod> | tee -a ~/Desktop/abc.json | kjq
    ```
    
3. **Interactive Filtering with Peco**: The problem with the above approach is that it doesn’t have interactive filtering which we get from Peco. I had to use the file that is being created in another tab/split:
    
    ```bash
    cat ~/Desktop/abc.json | peco
    ```
    
4. **<mark>Loggo - A Terminal UI App</mark>**<mark>:</mark> Just when I was about to create my own terminal UI app, I discovered this fantastic tool: Loggo - [https://github.com/aurc/loggo](https://github.com/aurc/loggo)  
    Loggo is a versatile tool with a range of features that make it a powerful asset for managing log streams. Here are some of its key features:
    
    1. **Stream Parsed Logs from a Persisted File**
        
    2. **Stream Parsed Logs from a Piped Input**:
        
    3. **Log Templates**: Loggo provides a tool for creating log templates. This allows you to define the structure of your logs, making it easier to parse and understand them.
        
    4. **Local Log Filtering/Search**:
        
    5. **Unaffected Main Log Stream**: This ensures that your original log data remains intact.
        
    6. **Display Only Matching Log Entries**: This helps to declutter your log view and focus on the logs that matter.
        

## Dive Deeper 📚

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700460650806/249b3310-4c7b-4436-8519-da79c352fe0e.png align="center")

> For a more detailed walkthrough of loggo, check out my previous blog post on loggo [here](https://hashnode.com/post/clp5oz9ov000408jm1jtpfusx).

I hope you find these tips as useful as I have. I’m looking forward to hearing your thoughts and feedback! 💬 Stay tuned for more productivity hacks and developer tips. Happy coding! ⌨️ 😄