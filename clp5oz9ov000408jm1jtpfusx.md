---
title: "Introducing Loggo: A Powerful Terminal App for Structured Log Streaming"
datePublished: Sun Nov 19 2023 16:28:11 GMT+0000 (Coordinated Universal Time)
cuid: clp5oz9ov000408jm1jtpfusx
slug: introducing-loggo-a-powerful-terminal-app-for-structured-log-streaming
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700410471407/9961f1d2-e3aa-4af2-b614-515a9f6b6f4a.png
tags: productivity, terminal, json, developer, debugging

---

# Introduction

As a software developer, I often find myself grappling with the challenge of parsing and viewing logs on the terminal. Without color coding and formatting, it can be a daunting task to make sense of the vast streams of data. But then, I discovered [Loggo](https://github.com/aurc/loggo) .

Loggo is a game-changer. It leverages the capabilities of your terminal to parse log streams based on JSON-based logs, bringing clarity and structure to what was once a sea of confusing data.The difference it has made in my day-to-day tasks as a developer is nothing short of impressive.

I highly recommend giving Loggo a try. It’s not just about making tasks easier, but also about enhancing your productivity and efficiency as a developer. Trust me, once you start using Loggo, you’ll wonder how you ever managed without it.

## How to Use Loggo? 🤔

### Installation

Installing Loggo is a straightforward process and the developers have provided detailed instructions for various methods of installation. You can find the complete installation guide on the \[official GitHub page\] of Loggo. The guide covers installation methods for different platforms and environments, including macOS/Linux with Homebrew/Linuxbrew, installation with Go, building from source, and downloading pre-compiled binaries. Make sure to follow the instructions that best suit your setup. Happy coding!

### Features

Loggo is a versatile tool with a range of features that make it a powerful asset for managing log streams. Here are some of its key features:

1. **Stream Parsed Logs from a Persisted File**: Loggo can read and parse logs from a persisted file. This means you can save your logs in a file and use Loggo to read and interpret them later. This is particularly useful for post-mortem analysis or for sharing logs with your team.
    
2. **Stream Parsed Logs from a Piped Input**: Loggo can also read logs from a piped input. This allows you to pipe logs from another process directly into Loggo, enabling real-time log analysis.
    
3. **Log Templates**: Loggo provides a tool for creating log templates. This allows you to define the structure of your logs, making it easier to parse and understand them.
    
4. **Local Log Filtering/Search**: Loggo offers local log filtering and search capabilities. This means you can filter and search your logs based on specific criteria, making it easier to find the information you’re looking for.
    
5. **Unaffected Main Log Stream**: With Loggo, the main log stream remains unaffected regardless of the source (gcp, pipe, file, etc.). This ensures that your original log data remains intact.
    
6. **Display Only Matching Log Entries**: Loggo displays only log entries that match your search/filter criteria. This helps to declutter your log view and focus on the logs that matter.
    

### Usage

**From Pipe:**

```plaintext
tail -f <my file> | loggo stream
```

#### Kubernetes

```plaintext
kubectl logs -f -n <namespace> <pod> | loggo stream
```

`Logs View`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700405789920/bedb1750-589d-4eea-9d83-289abaf45ab3.png align="center")

`Filtering Logs`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700405813153/613099a0-bb75-4e3b-9e64-7260b4f3e787.png align="center")

## Conclusion

Loggo is a powerful tool for developers who need to manage and understand log streams. Its rich Terminal User Interface and compatibility with various platforms make it a versatile tool in the developer’s toolkit. Whether you’re running applications locally or on a Kubernetes cluster, Loggo can help you make sense of your log streams.

[For more information, check out the project on GitHub<sup>1</sup>](https://github.com/aurc/loggo).