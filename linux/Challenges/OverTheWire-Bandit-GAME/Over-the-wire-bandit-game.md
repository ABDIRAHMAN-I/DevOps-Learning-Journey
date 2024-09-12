![My Custom Badge](https://img.shields.io/badge/OverTheWire-Bandit-Green)

## Table of Contents 📚

- [My Journey with OverTheWire Bandit](#my-journey-with-overthewire-bandit)
  - [Bandit Level 0](#bandit-level-0)
  - [Bandit Level 0 → Level 1](#bandit-level-0--level-1)
  - [Bandit Level 1 → Level 2](#bandit-level-1--level-2)
  - [Bandit Level 2 → Level 3](#bandit-level-2--level-3)
  - [Bandit Level 3 → Level 4](#bandit-level-3--level-4)
  - [Bandit Level 4 → Level 5](#bandit-level-4--level-5)
  - [Bandit Level 5 → Level 6](#bandit-level-5--level-6)
  - [Bandit Level 6 → Level 7](#bandit-level-6--level-7)
  - [Bandit Level 7 → Level 8](#bandit-level-7--level-8)
  - [Bandit Level 8 → Level 9](#bandit-level-8--level-9)
  - [Bandit Level 9 → Level 10](#bandit-level-9--level-10)
  - [Bandit Level 10 → Level 11](#bandit-level-10--level-11)
  - [Bandit Level 11 → Level 12](#bandit-level-11--level-12)
  - [Command Summary Sheet](#command-cheat-sheet)


#

<be>

> **💡 Note:** This guide uses simple command-line tasks to help you master basic Linux skills with OverTheWire’s Bandit.

#



<!-- Add Google Font for bubble/gaming effect -->
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">

<h1 align="center" style="font-family: 'Press Start 2P', cursive; color: #23FF16;">
  <br>
  <img src="Images/bandit.png" alt="Bandit logo" width="200">
  <br>
      The OverTheWire Bandit GAME
  <img src="https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg" alt="Linux Tux Icon" width="50">
  <br>
</h1>

<be>


##  My Journey with OverTheWire Bandit


As part of my journey to mastering Linux, I recently stumbled upon the **OverTheWire Bandit** game—and honestly, it’s been a game-changer for me. I chose Bandit because I wanted a fun, interactive way to apply my Linux skills in real-world scenarios, and it came highly recommended by the CoderCo team as a great starting point.

For those who haven’t heard of it, Bandit is a wargame that helps you sharpen your Linux command-line skills in a hands-on way. Each level throws a new challenge at you, pushing you to navigate directories, manipulate files, and use different commands to find hidden passwords and unlock the next level.

---

## 🔍 What I’ve Learned So Far:

- **Mastering Commands:** Bandit has been a fantastic way to get hands-on with the command line. I started with the basics like `ls`, `cat`, and `grep`, and as I progressed, I got into more advanced tools like `find`, `xargs`, and `ssh`. It’s given me tons of practice, and I’ve definitely sharpened my command-line skills.

- **Problem-Solving:** Every level in Bandit feels like solving a puzzle. You have to read carefully, think things through, and sometimes just try different approaches until something works. It’s really helped me become more methodical and patient when working through problems in Linux.

- **Scripting Practice:** Some levels push you to get creative by combining commands or even writing simple scripts. It’s been an awesome way to improve my scripting, something I wasn’t expecting to work on as much!

- **Security Awareness:** Along the way, Bandit throws in some important security concepts like file permissions and SSH. These things are critical, especially if you’re working in DevOps or managing servers. I picked up some useful security tips without even realizing it at first.

---

## 🤔 Challenges Faced:



---

## 💡 Why I Think You Should Try It:

If you're looking to boost your Linux skills, I highly recommend giving OverTheWire Bandit a shot. It's tough, but that's what makes it rewarding. Each time you beat a level, it’s a big W, and it’s really satisfying to see how your skills improve as you go. Plus, there’s nothing quite like that feeling of finally cracking a tricky challenge.

---


##  Bandit Level 0


### Level Goal
The goal for **Bandit Level 0** was to log into the game server using SSH. My task was to connect to the provided host using the correct port, username, and password. Once I logged in, I needed to visit the Level 1 page to move on to the next step.

### What I Needed:
- **WSL (Windows Subsystem for Linux)** as my terminal.
- **SSH access to the server:**
  - Host: `bandit.labs.overthewire.org`
  - Port: `2220`
  - Username: `bandit0`
  - Password: `bandit0`

### Steps I Followed:
1. First, I opened my **WSL terminal**.

2. I used the following command to log into the Bandit server:
   ```bash
   ssh bandit0@bandit.labs.overthewire.org -p 2220

3. Here’s what each part of the command did:

    - ssh: started the secure connection.
    - bandit0 was the username I used to log in.
    - bandit.labs.overthewire.org was the remote server I needed to connect to.
    - -p 2220 specified that I used port 2220 instead of the default port.  

4. When prompted, I entered the password: bandit0.

5. Once I successfully logged in, I had completed Bandit Level 0.

<!-- Fancy title and stylish box around GIF --> <div style="text-align: center; margin: 20px 0;"> <h2 style="font-family: 'Arial', sans-serif; color: #FF5722; font-size: 24px; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 10px;">Live Demonstration</h2> <div style="width: 400px; margin: 0 auto; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);"> <img src="images/Level0.gif" alt="Level 0 GIF" width="100%" /> </div> </div>
#
