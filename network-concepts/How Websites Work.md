# How Websites Work | TryHackMe Write-up

In this room, I learned how websites actually work behind the scenes. Before this, I used websites every day without really thinking about what happens when we open a webpage, click buttons, or submit forms. This room explained the basics in a simple way and helped me understand how web technologies interact with each other.

It also introduced some security concepts like sensitive data exposure and HTML injection, which made the room even more interesting from a cybersecurity perspective.

---

# How Websites Actually Work

One of the main things I understood from this room is that websites are basically a combination of frontend and backend technologies working together.

When a user enters a website URL in the browser:

1. The browser sends a request to a web server
2. The server processes the request
3. The website files are sent back to the browser
4. The browser displays the webpage to the user

This process happens extremely fast.

For example:

When someone visits `youtube.com`, the browser communicates with YouTube’s servers and receives files like:

- HTML
- CSS
- JavaScript
- Images and videos

The browser then renders everything visually for the user.

### Real-world importance

Understanding how websites work is important because almost everything today depends on web applications:

- Banking systems
- Social media
- Shopping websites
- Online classes
- Cloud platforms

For cybersecurity, this knowledge is very useful because many attacks target web applications.

---

# HTML and Its Role

I learned that HTML (HyperText Markup Language) is basically the structure of a webpage.

HTML is used to create:

- Headings
- Paragraphs
- Buttons
- Forms
- Images
- Links

Without HTML, webpages would not have any proper structure.

### Example

```html
<h1>Hello World</h1>
<p>This is a paragraph.</p>
```

This creates a heading and a paragraph on a webpage.

### Real-world use

Every website on the internet uses HTML in some form.

Examples:

- Login forms
- Registration pages
- Search bars
- Navigation menus

As someone learning cybersecurity, understanding HTML is important because many web vulnerabilities involve manipulating webpage elements or forms.

---

# JavaScript and Dynamic Websites

Another important thing I learned is how JavaScript makes websites interactive.

Without JavaScript, websites would feel static and boring.

JavaScript allows websites to:

- Update content dynamically
- Validate forms
- Create animations
- Handle user interactions
- Load content without refreshing the page

### Example

When you like a post on Instagram and the like count changes instantly without refreshing the page, JavaScript is working behind the scenes.

### Real-world applications

JavaScript is used almost everywhere:

- Social media platforms
- Online games
- Web applications
- Dashboards
- Streaming websites

For penetration testing and bug hunting, understanding JavaScript can also help identify vulnerabilities and understand client-side behavior.

---

# Sensitive Data Exposure

This section was actually very interesting because it focused on security mistakes developers sometimes make.

Sensitive data exposure happens when confidential information becomes publicly accessible accidentally.

Examples of exposed data:

- Passwords
- API keys
- User information
- Database backups
- Hidden files

### Real-world example

If a developer leaves sensitive files publicly accessible on a web server, attackers might access them directly through the browser.

For example:

```text
example.com/backup.zip
```

If the backup contains database credentials or user data, it becomes a serious security issue.

### What I understood

Security is not only about hacking tools. Sometimes simple mistakes can expose important information.

This section also made me realize why companies care so much about properly securing their websites.

---

# HTML Injection

This section explained how attackers can inject HTML code into webpages if user input is not handled safely.

For example, if a website allows users to post comments without filtering input properly, someone could inject HTML tags into the page.

### Example

```html
<h1>Hacked</h1>
```

If the website displays this directly, it changes the webpage content.

### Why this matters

Even though HTML injection may look simple, it can sometimes lead to bigger security issues depending on how the application handles user input.

### Real-world importance

This helped me understand why input validation and sanitization are very important in web development and cybersecurity.

---

# Overall Understanding

This room helped me understand that websites are not just pages on the internet — there are many technologies working together behind the scenes.

Some important things I learned:

- How browsers and servers communicate
- Role of HTML in webpage structure
- How JavaScript creates interactive websites
- Risks of sensitive data exposure
- Importance of input validation

I also realized that learning web fundamentals is very important before moving deeper into cybersecurity because most modern attacks target web applications in some way.

Overall, this room was beginner-friendly and gave a solid introduction to how websites work in real-world environments.
