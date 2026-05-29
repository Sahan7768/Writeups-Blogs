# Getting Started Right: My Journey Through the Hack The Box "Intro to Academy" Module

> *"Every expert was once a beginner. The platform you start on shapes the hacker you become."*

---

**Module:** Intro to Academy | **Platform:** [Hack The Box Academy](https://academy.hackthebox.com) | **Tier:** 0 (Free)  
**Sections:** 8 | **Difficulty:** Fundamental | **Category:** General  
**Author:** Cybersecurity Enthusiast | **Published:** May 2026 | **Read Time:** ~7 minutes

---

## Introduction

Before you can hack a machine, exploit a vulnerability, or enumerate a network, you need to know *where* you are and *how* your environment works. The **Intro to Academy module** on Hack The Box Academy is exactly that — a foundation-setting, platform-orienting first step designed for every new learner who walks through the virtual door.

It might seem like a formality. Eight sections, free of charge, no technical prerequisites. But treat it as such and you'll miss something important: a carefully designed onboarding experience that teaches you not just how to navigate a platform, but *how to think about structured learning in cybersecurity*.

This blog post breaks down everything I learned — about the platform, the philosophy behind it, and the habits it immediately starts building in you as a future security professional.

---

## 1. What Is HTB Academy, Really?

Most people find Hack The Box through the main platform — the gamified hacking environment with machines, challenges, and leaderboards. HTB Academy is different. It's an **educational arm** built specifically around structured, curriculum-driven learning.

HTB Academy's goal is to provide a highly interactive and streamlined learning process to allow users to have fun while learning. Content within Academy is based around the concept of "guided learning." Students are presented with material in digestible chunks with examples of commands and their output throughout, not just theory.

The key distinction here is **guided learning vs. pure exploration**. On the main HTB platform, you're dropped into a challenge and expected to figure it out. Academy holds your hand — just enough. It shows you the *what* and *why*, then immediately challenges you to apply it hands-on. That balance is intentional and effective.

Think of it this way:
- **HTB Main Platform** = The exam
- **HTB Academy** = The classroom that prepares you for the exam

Both are necessary. The Intro to Academy module makes this relationship crystal clear from the very start.

---

## 2. The Building Blocks: Modules, Sections, and Paths

One of the first things this module demystifies is the **structural vocabulary** of the platform. Before you can navigate effectively, you need to understand what you're navigating.

### Modules

Modules are like courses; they contain content confined to a specific subject, such as Linux Privilege Escalation or Windows Fundamentals. Each of these is its own discrete unit and has a certain cost of Cubes associated with it.

Every module is a self-contained learning unit. You can start and stop at any time, with no time limit or formal grading system. Your goal is simple: complete all sections and exercises.

### Sections

Each Module is broken up into Sections. These Sections are equivalent to one lesson in the topic covered by the Module. Some sections in the module only require reading through the material. Sections with the interactive icon include hands-on tasks or activities where you'll need to actively engage to progress.

This dual format — passive reading sections and active interactive sections — is one of the most effective pedagogical choices on the platform. Passive reading builds conceptual understanding; interactive sections force you to *apply* that understanding before moving on. You can't fake it.

### Paths

Paths are collections of related modules grouped into a learning track. For example, the **Information Security Foundations** path groups together modules like Introduction to Networking, Linux Fundamentals, and Windows Fundamentals — giving beginners a structured roadmap rather than a confusing catalogue of options.

---

## 3. The Cube System — HTB's Learning Economy

One of the more unique elements of HTB Academy is its **Cube economy** — an in-platform currency system that governs access to modules.

Cubes are the currency of HTB Academy. They operate as credits you can use to unlock the higher-tier Academy Modules. You can buy Cubes as either part of a subscription or as a one-off purchase. All accounts start off with 30 free Cubes.

Here's where it gets clever:

For example, a Tier 0 Module costs 10 Cubes, but you get all 10 Cubes back after completing the Module, making it completely free!

This cashback model does two important things:

1. **It removes financial barriers for beginners** — all Tier 0 modules (including this one) are effectively free as long as you complete them
2. **It creates a progression incentive** — completing modules funds your access to more advanced modules, rewarding consistent effort with expanded access

Each module costs a specific amount of cubes to unlock, and will always return 20% of those cubes back upon 100% completion of the module.

| Tier | Cost | Cubes Returned | Net Cost |
|------|------|----------------|----------|
| Tier 0 | 10 | 10 | **Free** |
| Tier I | 50 | 10 | 40 |
| Tier II | 100 | 20 | 80 |
| Tier III | 500 | 100 | 400 |
| Tier IV | 1000 | 200 | 800 |

The financial design of the platform is actually aligned with its educational philosophy: **invest in your learning, and the platform reinvests back into you**.

---

## 4. Subscription Models — Finding the Right Plan

The Intro module also introduces the two types of Academy subscriptions, which is worth understanding before spending money:

HTB Academy offers two different types of subscription models: Cube-based and Access-based. Cube-based subscriptions allow you to purchase Cubes every month at a discounted price. The Cubes are yours to spend as you please, and you will have permanent, life-long access to any Modules you unlock using them. Access-based subscription models grant you access to all Modules up to a certain tier for as long as you have the subscription.

**My recommendation as a beginner:**
- Start with free Tier 0 modules to explore the platform at zero cost
- Once you know you're committed, consider the **Student Plan** (access-based) for broad Tier 0–2 coverage
- As you advance toward certifications like CPTS or CBBH, evaluate Cube-based subscriptions for permanent access to specific high-value modules

There's no wrong answer — but understanding the model upfront prevents costly mistakes.

---

## 5. Pwnbox — Your Browser-Based Hacking Environment

This was one of the features that genuinely surprised me. Unlike many security training platforms that require you to set up a local VM, configure VPN connections, and troubleshoot networking issues before you can even start learning, HTB Academy provides something far more accessible:

HTB Academy is 100% browser-based! You can interact with all Module targets using a version of the Pwnbox built into each interactive Academy module section.

**Pwnbox** is a fully functional Parrot OS instance that runs directly in your browser. It comes pre-loaded with:
- Common penetration testing tools (nmap, gobuster, ffuf, Metasploit, etc.)
- A terminal you can use immediately
- A VPN connection to the target machines built-in

This means your onboarding barrier drops to essentially zero. No Kali Linux setup, no VirtualBox configuration, no networking headaches. You open the module, spawn the Pwnbox, and start hacking.

Free users are allowed one Pwnbox spawn per day. Each Pwnbox spawn allows for two hours of usage.

For those who prefer their own environment, VPN packages are available to connect your local machine directly to the Academy lab network.

> **Pro tip from the module:** Even if you're comfortable with your own VM setup, practice using Pwnbox early. In real-world assessments and CTFs, you may find yourself working from a restricted or shared environment — the ability to operate effectively from a browser-based terminal is a valuable skill.

---

## 6. The Guided Learning Philosophy — Why It Works

What separates HTB Academy from a YouTube playlist or a PDF guide? The module is quite explicit about this — and it's worth internalizing.

Students are provided target hosts where they can reproduce the materials presented in each section for themselves, hands-on exercises that serve as "checkpoints," and skills assessments to test their understanding of the material.

This mirrors a principle well-established in cognitive science: the **testing effect** (also called retrieval practice). Information you are *tested on* is retained far better than information you merely read. Every interactive section and skills assessment in HTB Academy is, in essence, a forced retrieval event — making your learning more durable.

The module also introduces the concept of the **Skills Assessment** — a capstone exercise at the end of most modules that requires you to apply *everything* you've learned without step-by-step guidance. You don't get to use hints here. You have to enumerate, think, and problem-solve independently.

This is the bridge between passive student and active practitioner. Completing a skills assessment successfully means you haven't just read about a concept — you've *demonstrated* it.

---

## 7. How HTB Academy Connects to the Main Platform

A question I had early on: *Does what I do on Academy count toward anything on the main HTB platform?*

Does my Academy activity contribute to my main Hack The Box rank and progress? No, but the content in Academy will indirectly help you solve a good deal of the content on Hack The Box.

The relationship is **preparatory, not integrated**. Think of Academy as the gym, and the main platform as the competition. You won't get trophies for gym sessions — but you'll win more competitions because of them.

The recommended progression most veterans suggest:

```
HTB Academy Fundamentals
        ↓
HTB Academy Offensive/Defensive Paths
        ↓
HTB Starting Point (guided machines)
        ↓
HTB Easy Retired Machines
        ↓
HTB Medium/Hard Machines + CTFs
        ↓
HTB Pro Labs / Certifications (CPTS, CBBH, CDSA)
```

The Intro to Academy module plants this map in your mind from day one.

---

## 8. First Interactive Exercise — Running Your First Command

One of the highlights of this module's interactive sections is the very first hands-on task: spawning a Pwnbox and running a basic Linux command to identify the system.

```bash
cat /etc/issue
```

This returns the OS distribution name — for the HTB Academy Pwnbox, that's Parrot OS. Simple? Yes. But the *act* of:
1. Spawning an instance
2. Opening a terminal
3. Running a command
4. Submitting an answer

...creates the habit loop that will repeat hundreds of times across your Academy journey. The first time you do it matters because it makes the process feel real and achievable. That psychological win is intentional.

---

## 9. Platform Navigation Tips I Wish I'd Known Earlier

The Intro to Academy module covers several platform features that are easy to overlook but save significant time:

**Table of Contents:** Every module has a right-side panel with all sections listed. Use it to track progress and jump between sections without losing your place.

**AI Translation:** You can use HTB's AI Translation features to translate the text of any module's section into your preferred language. This is a major accessibility feature for non-English speakers entering cybersecurity.

**Section Types at a Glance:**
- 📄 **Article icon** = Reading only, no interaction required
- 👆 **Interactive icon** = Hands-on task, must complete to progress

**Separate Accounts:** You need to register a separate account for HTB Academy. HTB kept it this way to let people who don't know how to hack their way into the HTB main platform get a chance at Academy easily. Don't get confused — your Academy profile and your main HTB profile are different, though you can use the same credentials.

---

## 10. Building the Right Mindset From Module One

Here's what I think is the most underappreciated aspect of the Intro to Academy module: it's not just teaching you how to *use* the platform. It's teaching you how to *approach* the platform.

The emphasis on:
- Reproducing examples yourself (not just reading them)
- Completing interactive exercises before moving on
- Working through skills assessments independently
- Using the Pwnbox hands-on, not just watching demos

...is all scaffolding for a fundamental mindset shift. In cybersecurity, **knowing the theory is not the same as being able to execute**. The platform is designed, from module one, to close that gap.

The habits you form in your first module carry forward. Students who skip exercises, look up answers without trying, or rush through sections to collect cubes will hit a wall in more advanced modules. Students who engage genuinely from the beginning build the muscle memory and problem-solving confidence that separates good professionals from great ones.

---

## Personal Reflection

I'll be honest: I almost skipped this module. Eight sections, "Fundamental" difficulty — it felt like filler before the "real" content.

I was wrong.

The Intro to Academy module gave me:
- A mental model of the platform I still rely on daily
- Confidence that I could navigate the environment effectively
- My first taste of the hands-on → theory → assessment loop
- An appreciation for *why* the platform is structured the way it is

If you're starting your HTB Academy journey, **do not skip this module**. Complete every section. Read every paragraph. Run every command. It takes less than two hours, and it pays dividends across everything that follows.

---

## Conclusion

The **HTB Academy Introduction to Academy** module is deceptively simple. On the surface, it's platform onboarding. Underneath, it's the first lesson in a broader curriculum on *how to learn cybersecurity effectively*.

It introduces the Cube economy, the Pwnbox, the guided learning philosophy, the module/section/path structure, and the connection between Academy and the wider HTB ecosystem — all in 8 short sections.

More importantly, it sets expectations. It tells you: *this platform will ask you to engage, not just observe*. And in a field where the difference between a certification holder and a skilled practitioner is the ability to *do* things under pressure, that expectation is everything.

---

## Resources & Next Steps

- 🔗 [HTB Academy — Intro to Academy Module](https://academy.hackthebox.com/course/preview/intro-to-academy)
- 🔗 [HTB Academy Help Center — Introduction](https://help.hackthebox.com/en/articles/12256202-introduction-to-htb-academy)
- 🔗 [HTB Academy Modules & Paths Guide](https://help.hackthebox.com/en/articles/12741910-academy-modules-paths)
- 📚 **Recommended next module:** [Learning Process](https://academy.hackthebox.com/module/details/9) — the cognitive framework behind effective security learning
- 📚 **Recommended path:** Information Security Foundations — the structured roadmap for absolute beginners
- 🛠️ **First challenge:** Complete the Intro module, then immediately start Linux Fundamentals

---

## Module Completion Checklist

Before moving on, make sure you can answer these questions from memory:

- [ ] What is the difference between a Module, a Section, and a Path?
- [ ] How does the Cube cashback system work?
- [ ] What is Pwnbox and how do you spawn one?
- [ ] What is the difference between an Article section and an Interactive section?
- [ ] How does HTB Academy connect to the main HTB platform?
- [ ] What is a Skills Assessment and when does it appear?

If you can answer all six confidently, you're ready for what comes next.

---

*Written after completing the HTB Academy Intro to Academy module. All thoughts are personal reflections intended to help fellow learners entering the cybersecurity field.*

---

> **"The journey of a thousand exploits begins with a single `cat /etc/issue`."**
