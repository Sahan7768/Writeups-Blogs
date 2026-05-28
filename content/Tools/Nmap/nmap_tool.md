# Nmap: Your Friendly Network Scanner

## What is Nmap?

Nmap, short for Network Mapper, is an open-source utility used to discover hosts, services, and security exposure on a network. In simple terms, it helps you answer questions like:

- Which devices are alive on the network?
- Which ports are open?
- What services are running behind those ports?
- Which versions of those services are exposed?

That makes Nmap useful for both learning and real-world security assessments. It is one of the first tools many cybersecurity students learn because it gives a clear picture of how a system is exposed from the outside.

## Why Do People Use Nmap?

People use Nmap for several practical tasks:

- **Asset discovery** - Identify hosts that are reachable on a network.
- **Port scanning** - Check which network services are exposed.
- **Service detection** - Learn whether a port is running SSH, HTTP, FTP, or something else.
- **Basic security review** - Spot unnecessary open ports and reduce attack surface.
- **Training and labs** - Practice enumeration in a safe environment such as TryHackMe or Hack The Box.

For a beginner, Nmap is not just about scanning. It teaches a core security habit: always understand what is exposed before you attempt to secure it.

## Key Ideas To Know

Before using Nmap, it helps to understand a few terms:

- **Host** - A device on the network, such as a laptop, server, or router.
- **Port** - A numbered entry point used by network services.
- **Service** - The application listening on a port, such as SSH or Apache.
- **Banner** - A small piece of information a service may reveal about itself.

These ideas matter because Nmap does not just tell you that a port is open. With the right options, it can also tell you what is likely running there.

## Common Nmap Commands

Here are some of the most useful commands for getting started:

| Goal | Command | What it does |
| :--- | :--- | :--- |
| Check whether a host is alive | `nmap -sn 192.168.1.0/24` | Performs host discovery without scanning ports. |
| Scan the default top ports | `nmap 192.168.1.10` | Checks the most common ports on a single host. |
| Detect service versions | `nmap -sV 192.168.1.10` | Tries to identify the software behind open ports. |
| Scan all TCP ports | `nmap -p- 192.168.1.10` | Checks every port from 1 to 65535. |
| Run a faster, more aggressive scan | `nmap -T4 192.168.1.10` | Speeds up timing for responsive networks. |
| Save results to a file | `nmap -oN scan.txt 192.168.1.10` | Writes the output in a normal text format. |

### Example: Basic Host Scan

```bash
nmap 192.168.1.10
```

This is the simplest way to start. If the host is reachable, Nmap lists the open ports it finds.

### Example: Service Version Detection

```bash
sudo nmap -sV 192.168.1.10
```

This is more informative because it attempts to identify the service and version behind each open port. That can help you understand whether a service is outdated or misconfigured.

### Example: Full Port Scan

```bash
nmap -p- 192.168.1.10
```

By default, Nmap scans the most common ports. If you want a broader view, this command checks all TCP ports. It takes longer, but it is useful during deeper enumeration.

## How To Read the Output

When Nmap finishes, you will usually see a list of open ports and matching services. A result may look something like this:

```text
PORT    STATE SERVICE VERSION
22/tcp  open  ssh     OpenSSH 8.2
80/tcp  open  http    Apache httpd 2.4
```

This means the host has SSH and HTTP exposed. From a security perspective, that tells you two things:

- Remote administration is allowed through SSH.
- A web server is publicly accessible on port 80.

That information is valuable during both assessment and hardening, because you can decide whether each service is expected.

## When To Use Nmap

Nmap is most helpful when you need a quick network map before deeper analysis. Use it when you want to:

- Inventory devices on a trusted network.
- Verify which services are exposed on a server you own.
- Prepare for a lab or CTF challenge.
- Check whether a machine is running more services than expected.
- Compare a system before and after a configuration change.

If your goal is endpoint malware analysis, memory forensics, or web application testing alone, Nmap is not the main tool. It is specifically a network reconnaissance tool.

## ⚠️ A Very Important Warning

**Only scan systems you are authorized to test.**

Scanning someone else's computer, school network, office network, or public target without permission can be illegal and unethical. Even if the scan seems harmless, you should treat network probing as sensitive activity.

✅ **Safe examples:** Your own computer, your home lab, your own test subnet, or training targets such as `scanme.nmap.org`

❌ **Unsafe examples:** Someone else’s Wi-Fi, a school or office network you do not manage, or random public IP addresses

If you are practicing, keep scans inside a lab, virtual machine network, or training platform.

## Good Beginner Habits

Start small and be deliberate:

- Scan one host at a time.
- Understand the output before running the next command.
- Save results so you can compare scans later.
- Use service detection only when you need more detail.
- Stay inside systems you own or have explicit permission to test.

## Short Conclusion

Nmap is one of the most practical tools in cybersecurity because it turns an unknown network into something you can understand. It helps you discover hosts, identify services, and spot unnecessary exposure.

If you are learning cybersecurity, Nmap is a strong place to begin. Use it in safe environments, practice the basic commands, and build the habit of reading the results carefully.

**Happy and safe scanning.**