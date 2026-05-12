# Virtualisation Basics | TryHackMe Write-up

In this room, I learned how virtualization works and why it is widely used in modern IT and cybersecurity environments. Before this, I already used virtual machines a little, but I did not fully understand how they actually work behind the scenes or why they are so important.

This room helped me understand how multiple operating systems can run on a single physical machine and how virtualization improves flexibility, testing, security, and resource management.

---

# What Is Virtualization?

Virtualization is the process of creating virtual versions of computer systems using software.

Instead of needing multiple physical computers, virtualization allows one physical machine to run multiple virtual machines (VMs).

Each VM behaves like a completely separate computer with its own:

- Operating system
- Storage
- RAM
- Applications
- Network configuration

### Real-world example

A person can run:

- Windows
- Kali Linux
- Ubuntu

all on the same physical laptop using virtualization software.

This made me understand why virtualization is so useful for learning, testing, and cybersecurity labs.

---

# Virtual Machines (VMs)

A virtual machine is basically a software-based computer running inside another computer.

Even though it is virtual, it behaves almost like a real physical machine.

### What I learned

A VM can:

- Install operating systems
- Run applications
- Connect to networks
- Store files
- Be isolated from the host system

### Real-world use cases

Virtual machines are commonly used for:

- Malware analysis
- Penetration testing
- Software testing
- Running multiple operating systems
- Cloud computing
- Server management

---

# Hypervisors

This room introduced hypervisors, which are responsible for managing virtual machines.

A hypervisor is the software layer that allows virtualization to happen.

### Its job

- Create VMs
- Allocate resources
- Manage virtual hardware
- Isolate systems

### Examples

- VirtualBox
- VMware
- Hyper-V

This helped me understand what actually controls and manages virtual machines behind the scenes.

---

# Resource Allocation

Another important thing I learned is that virtual machines share the host system’s hardware resources.

When creating a VM, resources like:

- RAM
- CPU cores
- Storage

must be assigned manually.

### Example

If the host system has:

- 16 GB RAM
- 8 CPU cores

then a VM might be allocated:

- 4 GB RAM
- 2 CPU cores

This taught me that virtualization depends heavily on hardware resources.

---

# Isolation and Security

One of the most useful features of virtualization is isolation.

Virtual machines are separated from the host system and from each other.

### Why this matters

If something goes wrong inside a VM:

- Malware infection
- System crash
- Misconfiguration

the host machine is usually not directly affected.

### Cybersecurity importance

This is extremely useful for:

- Malware testing
- Ethical hacking labs
- Running risky tools safely
- Practicing attacks in controlled environments

This section made me understand why virtual machines are heavily used in cybersecurity training platforms like TryHackMe and Hack The Box.

---

# Snapshots and VM Management

The room also explained how virtual machines can be managed easily using snapshots.

A snapshot saves the current state of a VM.

### Benefits

If something breaks during testing, the VM can quickly return to an earlier state.

This is very useful when:

- Testing malware
- Practicing exploits
- Learning Linux
- Experimenting with configurations

---

# Real-World Applications Of Virtualization

This room helped me realize how important virtualization is in modern computing.

### Common real-world uses

- Cloud infrastructure
- Enterprise servers
- Cybersecurity labs
- Software development
- Testing environments
- Data centers

Large companies often use virtualization to reduce hardware costs and improve efficiency.

Instead of buying many physical machines, multiple virtual systems can run on fewer powerful servers.

---

# How This Relates To Cybersecurity

This room was especially useful for cybersecurity understanding because virtualization is used almost everywhere in security labs and testing environments.

For example:

- Kali Linux often runs inside VMs
- Malware is analyzed inside isolated VMs
- Penetration testers use virtual labs
- Security researchers test exploits safely

Without virtualization, testing dangerous tools directly on the host
