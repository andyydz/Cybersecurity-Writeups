# Putting It All Together | TryHackMe Write-up

In this room, everything I learned previously about DNS, HTTP, web servers, and websites started connecting together properly. Earlier, I learned these concepts separately, but this room helped me understand the complete flow of what actually happens when someone visits a website.

It basically combined networking, DNS, HTTP requests, and web servers into one complete process.

---

# How Everything Works Together

One of the biggest things I understood from this room is that opening a website involves multiple technologies working together in the background within seconds.

For example, when a user enters a website like:

```text
google.com
```

a lot of things happen behind the scenes before the webpage finally loads.

### The overall process

1. Browser checks if it already knows the IP address
2. DNS lookup happens if needed
3. DNS server returns the correct IP address
4. Browser connects to the web server
5. HTTP/HTTPS request is sent
6. Server responds with webpage files
7. Browser renders the website

This process made much more sense after doing this room because previously I only knew small parts individually.

---

# DNS and Website Communication

This room helped me understand how important DNS really is for the internet.

Without DNS, users would need to remember IP addresses for every website instead of simple names like:

```text
youtube.com
github.com
google.com
```

The browser first needs the IP address before it can communicate with the web server.

### Real-world example

When someone opens `github.com`:

- DNS converts the domain into an IP address
- Browser connects to that IP
- Website data gets transferred back

This entire process usually happens in seconds.

---

# HTTP and HTTPS Communication

Another thing this room connected together properly was HTTP communication.

Once the browser gets the IP address, it sends an HTTP or HTTPS request to the server.

### Example

```http
GET / HTTP/1.1
Host: example.com
```

The server then responds with:

- HTML files
- CSS
- JavaScript
- Images
- Other resources

I also understood better why HTTPS is important.

HTTPS encrypts communication between the browser and the server, which helps protect:

- Passwords
- Login sessions
- Payment information
- Sensitive user data

This is why almost every modern website uses HTTPS now.

---

# Web Servers and Their Role

This section explained how web servers handle requests from users.

A web server basically stores website files and delivers them when requested by clients.

Some common web servers mentioned were:

- Apache
- Nginx

### What I understood

When thousands of users visit a website, the server handles requests and sends back responses continuously.

For example:

If a user requests:

```text
/index.html
```

the server locates that file and sends it back to the browser.

---

# Other Components Used in Websites

The room also introduced additional technologies and components that help websites run efficiently.

Some important concepts included:

### Load Balancers

Used to distribute traffic across multiple servers so one server does not become overloaded.

### Databases

Store website data like:

- User accounts
- Passwords
- Posts
- Messages

### CDN (Content Delivery Network)

Helps deliver website content faster by using servers located in different regions worldwide.

### Real-world example

Large platforms like YouTube or Instagram cannot rely on a single server because millions of users access them simultaneously.

So they use:

- Multiple servers
- Load balancing
- Databases
- CDNs

to handle huge traffic efficiently.

---

# How This Relates To Cybersecurity

One thing I realized from this room is that understanding how websites work is extremely important for cybersecurity.

Because if you understand:

- How requests work
- How servers respond
- How DNS works
- How web servers process data

then it becomes easier to understand how attackers target web applications.

For example:

- Misconfigured servers
- Exposed databases
- Weak HTTPS configuration
- Vulnerable web applications

can all become security risks.

This room made me realize that learning fundamentals is very important before learning advanced hacking techniques.

---

# Overall Understanding

This room was actually very useful because it connected multiple concepts together instead of teaching them separately.

Now I have a much clearer understanding of:

- DNS resolution
- HTTP/HTTPS communication
- Web servers
- Website infrastructure
- Real-world website architecture

Overall, this room helped me understand the complete basic workflow of how websites operate on the internet and why each component is important.
