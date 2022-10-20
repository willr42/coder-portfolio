# T1A1 Workbook

William Robertson

# Workbook Questions

# Q1: **Identify** and **explain** common and important components and concepts of web development markup languages

Currently, web development is compromised of three different languages. **HTML**, or HyperText Markup Language, which represents a document's structure. MDN describes this as "a basic building block of the web" (MDN Web Docs, 2018), as without HTML, there is no content to be displayed on the page. This isn't necessarily true with newer approaches to web content, which involve fetching content after an initial HTML page has been received, using JavaScript.

## HTML

HTML is composed of `tags`, which represent different elements on the page. A tag is a string or character surrounded by `<` and `>` characters. Most HTML tags _open_ and _close_. That is to say, any opened tag like `<p>` needs to be accompanied by a closing `</p>` tag. There are some HTML tags that do not require a closing tag, for example `<img>` and `<br>`.

Arguably, the three most important tags in HTML are `<html>` itself, which defines the start and end of the document, `<head>` which contains elements that are needed for rendering the page, but do not appear on the rendered page, and `<body>`, which specifically contains elements that display in the browser.

If a tag is inside another HTML tag, it's said to be a **child** of that element. In this way, HTML builds up a tree - with `<html>` as the root, containing `<head>` and `<body>`, and then building from there.

> There is one more important tag - to be properly processed by modern browsers, an opening tag of `<!DOCTYPE html>` is required. The reasons for this are historical, but it needs to accompany any HTML document to comply with this.

There are over 100 tags in the modern HTML 5 spec, including everything from `<h1>` to `<h6>` for headings, `<p>` for paragraphs, `<img>` for images, `<a>` tags for "anchors" - links to internal and external page content - to more esoteric tags like `<code>` for blocks of code, `<script>` for embedding JavaScript on the page or sourcing it externally, `<link>` for linking style sheets, and more.

With HTML 5, the most recent definition of the HTML spec, there was a recent shift towards **semantic elements**. These are elements that have meaning, unlike `<div>` which is meaningless and serves only to *div*ide content. These include tags like;

- `main`, for the main content of a page
- `article`, for an article that could be rendered elsewhere online
- `nav`, for navigation elements like links to other pages
- `header` & `footer` for the top and bottom of page content.

Every HTML tag can possess **attributes**. An attribute is an additional piece of information about the element. They don't appear as content, but affect the document. Examples include `class` and `id` that can be used in CSS, `href` for anchor links that represent the link destination, `src` for images that include the relative or absolute path to an image and more. They can be important for styling as mentioned above, for accessibility in the case of attributes like `alt` for alt-text, `for` for labelling input fields in a way that can be parsed by screen-readers, or in adjusting behaviour like `autoplay` for video and `autocomplete` for inputs.

With just HTML, a page would look rather plain, just a step above plaintext. Each browser applies some default styling, but they're quite barebones. To add significant styling to a HTML document, we need to add **CSS**.

## CSS

CSS stands for Cascading Style Sheets. CSS applies _styles_ to particular elements. The syntax for CSS is quite simple.

```css
p {
  color: red;
  width: 200px;
}
```

It uses **selectors**, which are typically HTML elements, classes, or IDs, but in more complicated situations, can include pseudo-classes like `:hover`. It then uses `{` and `}` characters to create a declaration block that contains various CSS properties and their values.

There are three ways to style an element. You can add a style **in-line** in the HTML itself, by adding a `style` attribute to an element. EG, `<h1 style="color:red">I'm red` would create an H1 element with a red colour. This can be useful, but can quickly get messy. The next is to add a `<style>` tag to the head of the document, and do styling in there. The most common way is to use an external stylesheet, or multiple external stylesheets. This is done using a `<link>` element, like this: `<link rel="stylesheet" href="./styles.css">`.

CSS is a fundamental part of the modern web, modifying the position, display, color, size of elements. Elements in HTML can be either "in-line" or "block", and this affects their ability to be styled or positioned on the page.

## JavaScript

The final element of web development is not really part of markup languages, but I'll mention it quickly, which is JavaScript. JavaScript, unlike HTML or CSS, is a **programming** language. It is used to add interactivity to the modern web. Mosts sites now extensively use JavaScript to do everything from listen to page events, change HTML elements on-the-fly, or even play games.

# Q2: Define the features of the following technologies that are essential in terms of the development of the internet: packets, IP addresses (IPv4 and IPv6), routers and routing, domains and DNS. Explain how each technology has contributed to the development of the internet.

## Packets

Packets are a way of ensuring throughput on a complicated network system, like the internet. Instead of sending one file in totality at once, which would create significant congestion between computers, we send a series of packets. Packets contain headers, which contain important metadata about the packet that can include the destination IP address, the source IP address, the hop limit, and more information. Packets also contain the payload, which is a portion of the data needed to construct the actual file that the destination computer wants to receive. The computer will receive thousands, or tens of thousands, of these packets, and reassemble them at the other end into the data requested.

The two most popular transmission protocols today, TCP and UDP, both use packets. Without packets, it would be almost impossible to run a network as big and as complex as the internet.

## IP addresses IPv4

An IP address is a unique number that identifies computers on a network. IP stands for Internet Protocol. It's a set of agreed-upon rules, invented in the 1970s, that define how data is sent and received over a network. Part of this protocol involves assigning a unique identifier to each computer, to ensure packets are delivered to the correct address. IPv4 specifically refers to the **fourth version** of the protocol, and is the one most-widely used today. IPv4 addresses are typically displayed as four numbers separated by full-stops, for example, 142.250.70.238.

More accurately, IPv4 uses 32 bits to represent addresses, which are broken up into four "octets" (groups of 8 bits each) (Ward, 2020). Certain ranges of IPv4 are specifically sectioned off for specific uses. `192.168.0.0 - 192.168.255.255` is the most common of these bands, which is a common default for most private networks. Another important one for web development is the "loopback address", `127.0.0.1`, which basically connects the machine to itself. Commonly called localhost, this allows us to run things like server programs on our local machine, and still visit them, even when offline.

IP addresses are fundamental to the Internet, in being able to determine the correct address to send a packet.

This 32-bit address space is extensive, but as more and more online devices have been produced and disseminated internationally, it became clear that IPv4 would not be enough to address every device. That led to the invention of IPv6.

## IP addresses IPv6

IPv6 is the **sixth version** of the IP protocol. (IPv5 was never adopted, as it used IPv4's old 32-bit addressing.) From IPv4's 32 bits, IPv6 contains **128 bits**. In contrast to the dotted quad notation common to IPv4, IPv6 uses hexadecimal representation, where each digit is represented by a character from 0 to f (Base 16 notation). An example IPv6 address would be something like 1080:0000:0000:0000:0008:0800:200C:417A (Blank, 2004). This has solved the issue of address space, taking the range of possible IP addresses from IPv4's roughly 4 billion to a frankly almost unwriteable number - 340 trillion trillion trillion, per RedHat (2019).

IPv6 will ensure that the Internet can continue to add devices indefinitely, and sidesteps an almost Y2K-scale problem that was rapidly looming.

## Routers & Routing

At their most basic level, routers "route" packets, connecting two networks together. This is necessary, because it would be impossible for the entirety of the internet to inhabit the same one shared network - computers need to listen for packets being sent to them, and transmit further packets onwards, all of which creates congestion on the line. Routers solve this issue, by breaking the internet (and other networks) up into smaller subnetworks.

For example, at home, every one of us who has a WiFi network has a Local Area Network, or LAN. To connect this LAN to the wider internet, we need a router. The router translates the packets being received from our Internet Service Provider's Wide Area Network (WAN) to ones that then go onwards through the LAN to the computer that requested them. A router allows all the devices in one home to "share" an IP address. The router uses an internal routing table to check the destination of each packet, and then send it on to the correct device.

Routers are the backbone of the Internet. Without them and their ability to divide networks, the Internet would have died through overwhelming congestion, and a maximum limit on the amount of devices that could be connected.

## Domains & DNS

Remembering a specific IP address is quite difficult. Furthermore, as organisations expand, they may have multiple IP addresses that serve the same content, or a more complex configuration of load-balancers, gateways and routers. It's far easier to remember a word. That is where domains come from. Domains are effectively an **alias** for a particular IP address, a word in string format that your computer can "resolve" to the actual IP address you want to visit.

Domain resolution is a multi-step process, with some limited hostnames stored on your system itself. However, the most common way of resolving domains is to use a Domain Name Server, or DNS. There is a network of DNS servers throughout the world that provide name resolution services for the entire internet. Domains, as they sound like, are different categories of host names - ".com", ".edu", ".net", are all **top-level domains**.

Domain resolution works like this. First, your computer checks its limited local host files (these differ from OS to OS). Then, if your host isn't listed there, your computer will ask your specified DNS server (this may be provided by your ISP, or you may choose your own). This server basically keeps a gigantic database that matches domains to IP addresses. However, that might not be enough. If your domain isn't in your DNS, your DNS will go ask a Root Name Server. There are only thirteen of these worldwide, and they "point" at the various top-level domains. Your DNS will then go ask the .com domain for the domain, and hopefully serve you the page. If there are subdomains, your DNS continues to ask until it gets the answer, or an error.

DNS is essential to the functioning of the Internet, allowing people to remember short web addresses rather than full IP dotted quads.

# Q3: Define the features of the following technologies that are essential in terms of the development of the internet: TCP, HTTP and HTTPS, web browsers (requests, rendering, developer tools)

## TCP

TCP stands for Transmission Control Protocol. It is part of the main protocol that defines the internet, the other of which is the Internet Protocol (IP), and together they are usually referred to as TCP/IP. IP is the protocol that defines the concept of IP addresses and moving packets from a source address to a destination address. However, it doesn't define the transmission of these packets. They could arrive at the destination in the wrong order, or one could fail to arrive at all. TCP prevents this, by defining a connection standard that takes place between two devices.

Every TCP connection starts with establishing the connection, also called a "TCP handshake". This handshake is three-way. (Blank, 2004).

1. The first computer sends a SYN packet, which means "SYNchronise".
2. The second computer sends a SYN/ACK packet, which means, "SYNchronise ACKnowledged".
3. The first computer sends an ACK packet, which means "ACKnowledged."

After the handshake, the computers can begin exchanging packets. Each packet contains a sequence address, and must be ACKnowledged by the receiving computer. This ensures no packets can be lost along the way, and that packets can be properly reassembled at the other end. Once the exchange is complete, another three-way handshake takes place, with SYN being replaced by FIN, for "FINished".

TCP is what enables clients to receive files from a server, in ensuring packets can be reassembled in the right order, and resent if they fail to be delivered.

## HTTP and HTTPS

HTTP stands for HyperText Transfer Protocol. It builds on top of TCP/IP and is the foundation of the World Wide Web, in that it defines the exchange that takes place between your web browser or other application and a web server. This exchange begins with an HTTP request from an application running on a computer. By convention, HTTP servers are hosted on port 80, so it's most common to send a request to this port (and it's the default used by most browsers, or it was up until the advent of HTTPS). This request contains (Blank, 2004, p. 61);

- the version of HTTP being used
- the URL, or Universal Resource Location, of the "resource" or page you are requesting
- the HTTP method of the request
- HTTP request headers
- an optional body.

The HTTP method is defined by the HTTP protocol, and contains a list of standard "verbs" that servers respond to. The most common are GET, which is to request a resource, POST, which is to send information to the server from the client, UPDATE, which updates information already existing on the client, and DELETE, which asks the server to delete a resource. Following the request, the web server sends a HTTP response, that contains similar data to the request, including a body that may consist of JSON data, a HTML document, a CSS document, an arbitrary file or more.

In this way, we can build a frontend client that sends HTTP requests to a backend server and displays the information.

The one flaw with HTTP is that these requests and responses are sent "in the clear", which means any other computer on the network or indeed along the path of the packet may intercept the packet and inspect it. Malicious actors may "sniff" the traffic and reveal personal information, or identify common usage patterns.

HTTPS solves this by asking websites to provide a Transport Layer Security certificate (formerly an SSL, or Secure Socket Layer, certificate, and the terms are often used interchangeably). These certificates are given out by Certificate Authorities, and require you to prove that you are who you say you are. This certificate is used to create an encrypted session between the client and the server, which means we can trust the traffic.

## Web Browsers

A web browser is most people's everyday experience of the internet, and have become essential tools in business and life in general. Web browsers are software that make requests to web servers, receive HTML, CSS, and JavaScript, and then render the page.

Rendering the page involves taking the HTML, which represents the structure of the page, layering on the CSS, which represents the styling, and using JavaScript to add interactivity to the page. New web technologies such as React have shifted the responsibility of rendering HTML to JavaScript itself, enabling Single Page Applications that happen in a single window without requiring a browser refresh.

Web browsers use URLs, which can be either domain names or raw IP addresses, to make HTTP(S) requests. Initially, the web was quite simple (before the existence of CSS and JavaScript) and thus were web browsers. Today, the web is as complex as any desktop frontend application, and browsers have had to keep pace.

With the majority of modern life taking place on the Internet, and a significant portion of that being in web browsers, having adequate developer tools in a browser is more important than ever. All major browsers feature **developer tools** integrated in them. You can inspect the HTML, CSS, and JavaScript, make changes to them on the fly, add debugging points to JavaScript code, live edit styles, watch the flow of network traffic, and hundreds more features.
   List of topics containing ethical issues:

   - access to a user’s personal information (medical, family, financial,
     personal attributes such as sexuality, religion, or beliefs)
   - intellectual property, copyright, and acknowledgement.
   - criminal acts such as theft, fraud, trafficking and distribution of prohibited substances, terrorism
   - GPS tracking data and other types of metadata, MAC addresses, hardware fingerprints
   - freedom of thought, conscience, speech and the media
   - aggressive sales and marketing practices designed to mislead and deceive consumers
   - trading of shares on the stock exchange OR crypto-currencies

8. Explain control flow, using examples from the Python programming language
9. Explain the difference between type coercion and type conversion. Are either of these used in Python?
10. Explain data types, using examples
11. Here’s the problem: “There is a restaurant serving a variety of food. The customers want to be able to buy food of their choice. All the staff just quit, how can you build an app to replace them?”

- Identify the classes you would use to solve the problem
- Write a short explanation of why you would use the classes you have identified

12. Identify and explain the error in the code snippet below that is preventing correct execution of the program

```python
celsius = input()

farenheit = (celsius*9/5)+32

print(f"The result is {farenheit}.")
```

13. The code snippet below looks for the first two elements that are out of order and swaps them; however, it is not producing the correct results. Rewrite the code so that it works correctly.

```python
arr = [5, 22, 29, 39, 19, 51, 78, 96, 84]
i = 0
while (i<arr.len()-1) and (arr[i] < arr[i+1]):
	i += 1
print(i)
	arr[i] = arr[i+1]
	arr[i+1] = arr[i]
```

14. Demonstrate your algorithmic thinking through completing the following two tasks, in order:

    1. Create a flowchart to outline the steps for listing all prime numbers between 1 and 100 (inclusive). Your flowchart should make use of standard conventions for flowcharts to indicate processes, tasks, actions, or operations
    2. Write pseudocode for the process outlined in your flowchart

15. Write pseudocode OR Python code for the following problem: You have access to two variables: raining (boolean) and temperature (integer). If it’s raining and the temperature is less than 15 degrees, print to the screen “It’s wet and cold”, if it is less than 15 but not raining print “It’s not raining but cold”. If it’s greater than or equal to 15 but not raining print “It’s warm but not raining”, and otherwise tell them “It’s warm and raining”.
16. ACME Corporation are hiring a new junior developer, as part of their hiring criteria they've created a "coding skill score" based on the specific competencies they require for this role; the more important the skill is for ACME corp, the more points it contributes to the "coding skill score" The skills are weighted as follows:

- Python (1)
- Ruby (2)
- Bash (4)
- Git (8)
- HTML (16)
- TDD (32)
- CSS (64)
- JavaScript (128) ​

Write a program that allows a user to input their skills and then tells them

- Their overall "coding skill score"
- Skills they may want to learn, and how much each one would improve their score
