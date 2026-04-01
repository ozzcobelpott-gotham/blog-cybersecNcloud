---
title: "What is an IP and how does it work? - Part 1"
date: 2026-03-26T17:02:42-06:00
draft: false
translationKey: "ip-01"
tags: ["Networks", "Basics", "Infrastructure"]
categories: ["Networks"]
---

> **Cobblepot Report:** *All internet communication, from sending a WhatsApp message to connecting to an application used by millions of users like Netflix, depends on knowing who is talking to whom. Understanding IP addresses isn't just "IT stuff"; it's the first step to understanding how digital services work, configuring websites, or understanding the foundations of cybersecurity. Without IPs, there is no digital business.*

---

# Understanding the Internet from the Ground Up: IPs

The internet may seem like black magic, but in reality, it operates under fairly strict and logical rules. Think of the internet as the world's largest and fastest mail system.

In this series, we're going to break down three fundamental concepts that have made it possible for you to be reading this blog right now:

1. What is an IP address (and why are we running out of them)?
2. How do ports and connections work?
3. How does all this relate to URLs?

Let's take it one step at a time, as Jack the Ripper said. Let's start with the basics.

---

## Part 1: What exactly is an IP address?

### The Unique Identifier of Your Devices

An IP (Internet Protocol) address is the unique identifier of a device within a network.

### What is a Network?

Think of a network as an apartment building with several people living on each floor. The network can be residential (a building where people live), corporate (an office building), or public (a shopping mall).

Each of these networks operates under specific rules, but for practical purposes, we'll focus on home networks—the building where people live, or in our case... the modem providing internet access in your home.

Without the network, your computer (or cell phone) would be like someone trying to receive mail in that building, but the mail carrier has no physical address to deliver it to; the data (letters in this example) simply wouldn't know how to get there.

Think of an IP address as a unique and unrepeatable number within the same environment. Your cell phone, your Smart TV, your smart refrigerator... they all have one. In the apartment example, there can't be two apartments with the number 1 (in a perfect scenario). If there were two apartments with the same number, they would probably share more than just the number itself—for example, bills. In the case of the network, they would share information if there are two identical ones.

---

### What does an IP address look like? What makes up an IP address?

If you have no prior knowledge, you might think that an IP address is something mystical, or a physical address like in the apartment example. In reality, it's simply a mathematical formula, from the 1980s, that solved a very big problem: How can we communicate with other people over the internet?

Here's an IP address in IPv4 format (don't worry, you'll understand this later):

`192.168.1.1`

This IP address is made up of four sections separated by periods. Each section is called an *octet*. The numbers within each octet can range from 0 to 255. (And yes, the IP address `1.1.1.1` exists, and it currently belongs to Cloudflare).

You might be wondering why an "octet" is called an "octet"... Well, an octet is a unit of digital information made up of 8 bits.

A bit (or binary digit) is the smallest unit in computing, since each bit can only be 0 or 1, resulting in possible combinations ranging from '00000000' (8 times 0) to '11111111' (8 times 1).

You may have also wondered why an octet can only range from 0 to 255. Well... if we apply a little math, we can find out exactly how many combinations an octet has:

A bit consists of only 2 possibilities, 0 and 1. This will be our constant "2," called "possibilities."

Each octet consists of 8 bits, that is, 8 possible combinations between 0 and 1, one for each bit. This will be our constant "8," called "number of bits."

The formula is simple: constant ^ number of bits:

2^8 = 256 possibilities.

That's why each octet can range from 0 to 255, where 0 = `00000000` and 255 = `11111111`.

These octets, or groups of 8 bits, are commonly known as *bytes*, which is a larger unit of measurement, also made up of 8 bits. So, our IP address, which contains exactly *4 octets* or *32 bits*, is also *4 bytes* of information.

---

### The Big Mistake of IPs

Imagine it's the 1980s, the beginning of the internet as we know it, and the number of people with access to this service is small and very limited because it's a recent invention.

As the years go by, and technology advances, more and more devices are added to the network.

* Now, knowing that IPs are not unlimited and they are limited by the structure of 4 different octets.

* This allows for approximately 4.3 billion possible addresses.

* In 1983, the TCP/IP protocol was created with the first official version of the 4-octet IP address (IPv4).

* By 1990, there were 5.27 billion people worldwide.

* The internet was opened to public access (World Wide Web) on August 23, 1991.

* In 1990, there were approximately 2.61 million users browsing the internet.

* By 1995, there were approximately 39.2 million users. This represents an increase of 1401.916% in 5 years.

* If the increase in internet users continued at this rate, it would mean that by the year 2000 there would be 549.2 million users. (Assuming only one device per user connected to the internet, excluding companies with numerous connected devices and devices connected but without a specific user, such as servers.)
* With this in mind, it was quite obvious that sooner or later IP addresses would run out worldwide. What would happen if they did? New devices needing to connect wouldn't have an address to connect to the global network.

- How would you solve this problem?

### Public or Private? What if there are two different buildings, but both have an apartment "1"?

To deal with the fact that we ran out of IPv4 addresses, something brilliant was invented, but it would eventually suffer the same fate: separating IPs into public and private.

* Let's go back to the building example. Right now, you're living in an apartment with the number "21" on the door.

* You need to receive a packet and you enter your address as "apartment with door 21".

* The delivery person arrives, but there's a huge surprise: in your neighborhood, there are 20 buildings just like yours, and they all have an apartment numbered "21." How is it possible that someone could find your address without a 1/20 chance of making a mistake?

* Imagine the same thing happening on the internet. You're sending a message, but it doesn't reach the intended recipient; instead, it goes to someone else, and a message that wasn't meant for you ends up in your hands... Chaotic, right?


 **Let me introduce you to the division of "IP addresses." (This is the same principle used in apartment buildings in real life.)**

* **Public IP Address:**
   * This is the face of your network to the outside world (the internet).

   * Your internet provider automatically assigns you *a single* IP address when you subscribe to the service, directly on your modem or router.

   * Continuing with the building example, this number is the external reference number outside your building.

* **Private IP:**
   * Only works within your home or office Wi-Fi network.*

   * Your router assigns these IPs to each device connected to that Wi-Fi network.*

   * These are like apartment numbers within a building. For example, there could be building 3 with apartment 22, and the internet service provider will know how to reach it if you provide both.

> **Fun Fact:** Your cell phone and laptop probably have the same public IP address right now (your home router's), but they have different private IP addresses to prevent conflicts. They're in the same building, but they belong to different apartments. Both should receive mail, but it might not be the same mail or at the same time.

---

### What does a private IP address look like?

Let's take this classic example that you'll probably see when talking about private IP addresses:
`192.168.1.25`

It's not just a random number. It's divided into two main parts, invisibly separated by something called a "subnet mask":

1. **Network:** Identifies which "neighborhood" or network the device belongs to. In this case, the neighborhood is `192.168.1`.

2. **Host (Device):** Identifies the specific device within that neighborhood. In this case, you are device number `25`.

This is how your devices can connect to your Wi-Fi; each one is assigned a "Host" under the same "Network".

* Can there be two IPs on the same network that share a Host? Absolutely not.

* What numbers can be in the Host? It ranges from 1 to 254.

* Why aren't 0 and 255 included? Well, these are two Host addresses reserved for special purposes within your Wi-Fi network. (Actually, this is for your router, but that's a topic for another day.)
* How would two devices on the same network appear? E.g., 192.168.1.104 and 192.168.1.200

---

### How do you get your "department" ID number?

There are two main ways a device connecting to Wi-Fi obtains its IP address:

* **Static (Manual):**

* It is manually configured and never changes.

* It is vital for web servers, office printers, or security cameras because you always need to know where to find them.

* **Dynamic (Automatic):**

* It is assigned all thanks to a protocol called DHCP.

* When you arrive at a coffee shop and connect to its Wi-Fi, the router "lends" you an IP address for a while. When you leave, it gives it to someone else.

* Every time you connect and disconnect from Wi-Fi, your private IP address will most likely change.

---

### What happens if public IP addresses run out?

We've done the math, we've discussed the history, and you probably have a question:
- "If there's a limit to the number of IP addresses, can public IP addresses run out?"

The answer to your question is a resounding 'YES'. But we also have a solution to the problem of underestimating the size of the internet.

Let me introduce you to the two existing versions of IP addresses.

### IPv4 (The old reliable)
It's the one you see every day.

* **Format:** `192.168.1.1`
* **Anatomy:** 4 numeric blocks, separated by periods, ranging from 0 to 255.
* **Capacity:** It allows for approximately 4.3 billion possible addresses.

* **The Big Problem:** In the 1980s, this seemed like an infinite number. Today, with everyone owning a cell phone, laptop, and smartwatch, **we're already running out of them**.

### IPv6 (The Savior)
It was created to solve the scarcity problem.

* **Format:** `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
* **Anatomy:** 8 alphanumeric (hexadecimal) blocks separated by colons.

* **Capacity:** Absurdly gigantic. We're talking about approximately 340 undecillion addresses. We could assign an IP address to every atom on the Earth's surface and still have some left over. It's designed to support the Internet of Things (IoT) for centuries.

In everyday life, you're likely to hear a lot about older versions (IPv4), especially in the context of servers.

If there's a much better, more powerful version on steroids... why are we still using the previous one?

Well, it turns out that implementing this version is complex because it lacks compatibility with its older sibling (IPv4), in addition to technical and, above all, economic barriers to migrating from one to the other. "Dual-stack" technologies were invented to allow both versions to coexist, even on the same network. (Your cell phone has an IPv6 address assigned by default).

---

### In short...

Imagine the postal system:
* **The Public IP Address** is the address of your residential building.

* **The Network** is the apartment building.

* **The Host** is your specific apartment number.

* **Dynamic/Static** is the difference between renting an Airbnb for a day or buying your own home.

In the next post, we'll see what happens once the letter arrives at your home and how the **Ports** ensure it's delivered to the correct person.