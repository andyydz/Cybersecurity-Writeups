# DNS in Detail | TryHackMe Write-up

In this room, I learned how DNS actually works behind the scenes and how devices convert domain names into IP addresses. Before this, I only knew that DNS connects domain names to websites, but this room explained the complete process in a much better way.

---

# Task 1 — What is DNS?

So basically, DNS stands for Domain Name System.

Instead of remembering IP addresses like `172.217.160.142`, we use domain names like `google.com`. DNS helps convert those human-readable domain names into IP addresses so computers can communicate with each other.

You can think of DNS like the internet's phonebook.

For example:

- User types `google.com`
- DNS finds the correct IP address
- Browser connects to that server

Without DNS, we would have to remember IP addresses for every website.

### Main things I learned

- DNS translates domain names into IP addresses
- Computers communicate using IPs, not domain names
- DNS makes browsing easier for humans

---

# Task 2 — Domain Hierarchy

This section explained how domains are structured.

I learned that domains are arranged in levels.

Example:

```text
subdomain.example.com
```

### Breakdown

- `.com` → Top Level Domain (TLD)
- `example` → Second Level Domain
- `subdomain` → Subdomain

This made it easier to understand how websites are organized.

### Examples of TLDs

- `.com`
- `.org`
- `.net`
- `.edu`

I also learned that DNS works in a hierarchical way, starting from the root servers and moving down step by step until the correct IP address is found.

---

# Task 3 — Record Types

This was one of the most important sections.

I learned about different DNS record types and what they do.

### A Record
Maps a domain name to an IPv4 address.

Example:

```text
google.com -> 142.250.x.x
```

### AAAA Record
Maps a domain to an IPv6 address.

### CNAME Record
Used to point one domain to another domain.

Example:

```text
blog.example.com -> example.com
```

### MX Record
Handles mail servers for email routing.

### TXT Record
Stores text information, often used for verification or security purposes.

This section helped me understand that DNS is not just about websites — it also handles emails and other services.

---

# Task 4 — Making A Request

This task explained what happens when we visit a website.

The process was actually interesting.

### Basic Flow

1. User enters a domain name
2. Browser checks cache
3. Request goes to DNS resolver
4. Resolver contacts DNS servers
5. Correct IP address is returned
6. Browser connects to the web server

I learned that DNS lookups happen extremely fast, even though multiple servers may be involved in the process.

---

# Task 5 — Practical

In the practical section, I used DNS-related tools and observed how DNS records work in real scenarios.

This helped me understand the concepts much better compared to only reading theory.

### What I practiced

- Looking up DNS records
- Understanding domain resolution
- Observing how requests are handled

---

# Final Thoughts

Overall, this room gave me a much better understanding of how DNS works internally.

Before this room, I only knew that DNS connects domains to websites, but now I understand:

- How domain hierarchy works
- Different DNS record types
- How DNS requests are processed
- Why DNS is important for the internet

This room was simple, beginner-friendly, and actually useful for understanding networking fundamentals.
