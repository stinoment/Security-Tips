\# 🚨 How do hackers target us developers? (Autopsy of a dirty phishing attack!)



!\[Almost Hacked](Almost-Hacked.jpg)



Hey everyone 👋



Today, I received an email seemingly from "WordPress" with an alarming tone: \*"To prevent your account from being suspended on https://user-sell.com/, you must verify your email immediately!"\* (I've attached the screenshot).



The email's appearance and the sense of urgency it created were very realistic. But well, my developer instincts told me something was off! 🧐 I dug deeper and inspected the links. The result? I came across 3 interesting technical tricks that hackers used to bypass users and security systems. 



Let's dissect this trap together:



\### 1. Sender Address Spoofing 🎭

In the email UI, the sender's name was elegantly written as \*Account by Wordpress\*. But when I checked the email headers, the real sender address was:

`mike.kraidie@tolkanu .se`

Does WordPress use a random personal Swedish (`.se`) domain to send official emails? Definitely not! That was the first red flag. 🚩



\### 2. Exploiting Open Redirect Vulnerability 🔀

Hackers know that if they put their phishing link directly in the email, Google and Yahoo spam filters will catch them instantly. So what did they do? They used the "Open Redirect" technique!

The main link looked like this:

`https://sbintl .com/Home/EnglishPage?url=https://trovazin-store .com/...`

What does this mean? The user first enters a legitimate, compromised site (`sbintl .com`) to bypass security filters, and then that same site immediately redirects the user to the hackers' main domain (`trovazin-store .com`)!



\### 3. Psychological Trick with Base64 Encoding 🧠

This is the most fascinating part! At the end of the hacker's link, there was a strange parameter:

`?=aC5hc2doYXJ...\[rest of the code]`

This isn't a random string; it was my email address encoded in \*\*Base64\*\* format! 

\*\*Why do they do this?\*\* Because when that fake login page opens, the hacker's JavaScript reads this parameter and pre-fills your email into the Login box. This makes you think: \*"Oh, it recognized my site, so it must be legit!"\* and without a second thought, you just enter your password! Simple as that.



💡 \*\*Final thought:\*\*

The technologies we developers use every day (like Base64 or redirects) are the exact same tools hackers use against us. 

Never trust the sender's name blindly, and always hover over or inspect links before clicking on important buttons.



Have you ever encountered a phishing attempt with this level of technical detail? Share your experience below so we can learn together. 👇



`#WebSecurity #WebDevelopment #Phishing #Programming #WordPress #SEO #JavaScript #CyberSecurity`

