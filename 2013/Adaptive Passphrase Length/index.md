---
title: Adaptive Passphrase Length
author: admin
date: 2013-07-31 11:57:09
categories:
  - Passwords
  - Security
tags: 
  - anecdote
  - arbitrary
  - blacklist
  - buzzword
  - cryptography
  - duress
  - gps
  - ip address
  - key pattern analysis
  - letter
  - location
  - locker
  - masterlock
  - midnight
  - obscurity
  - passphrase
  - password
  - pe
  - pie
  - safe
  - security
  - story
  - stroke
  - stylometrics
  - transmission
template: article.jade
---

Longer passwords are more secure. But if you've ever been on a website or computer network which mandated that you change your password every 30 days to a string which you haven't used in the past 180 which could not contain any part of your username or an English language word without being liberally adorned with num3r1cal and sy#b@!ic substitutions and aRbiTRarY capitalization, you should be able to understand the pain of long and arcane passwords.

At time of writing, I'm a high school senior with something on the order of three weeks left in school. I can't help but feel a tad wistful of the four years I've spent roaming these red-tinted halls of learning. Many of the particularly bittersweet memories include PE, a mandatory elective for my freshman and sophomore years. A bizarre policy forbid the possession of backpacks in the locker rooms, leading to the acquisition of the skill to open rotary combination padlocks, a skill which I just as quickly dispossessed myself of, having absolutely no need for a locker after that.

During that time, I had read about a pretty nifty hack involving Master Locks at the time. If you entered the combination and opened the lock and closed it again and left it on the last digit, you could open it again by rotating clockwise by fifteen and rotating back to the final digit (to fight the possibility of attackers who are aware of the exploit, you could turn the dial clockwise some number less than 15 after locking it, so that you would only have to remember the final digit). It was this trick that I used to open my locker just about every other school day for those  two years- a reduction in security no doubt, but a great convenience. I've been thinking over the design of the lock recently, and I'm not sure if it's better classified as a bug or a feature. Conventional wisdom dictates that no doubt this substantial reduction in the key space is a rather severe design flaw. The fact that many newer locks were immune (a lot of locks will snap the dial forward when closed so that it is physically impossible to land on the final digit) to this trick seems to support the notion that this was somehow an undesired consequence of locksmithery rather than some kind of delightful accident.

But the more I think about it, the more this bug seems like a feature. Perhaps the loss of security isn't nearly as egregious as it appears, and this little shortcut is actually a delightful little accident. Nearly every school day, I'd only have to take four seconds to open my locker because of this handy trick, except on those occasions some kid before me decided to walk around the lockers to press their heads against the metallic locks to spin them and pretend they can lock-pick, in which case, I'd have to enter the whole combination to _open __sesame_. That is, you only need to know one number to open it unless someone earlier guessed wrong, in which case, you'd have to enter three numbers.

The next story is about an iPhone.

I playfully grab at a friend's phone for the second time in a week. A friend takes a selfie using the newly emancipated phone, with a rather contorted grin. I dutifully replace her lock screen photo, which had previously been an aerial shot of her grassy picturesque college campus with my friend's contorted close-up selfie. She learns to be a bit more protective about her phone, quickly issuing a light tap on the power button to reengage the lock screen, a four headed Cerberus with an exponential backoff growl. But this doesn't mean anything to the enterprising background changer, because the unlocking gesture happens all the time and it's fairly easy to figure out what numbers someone's typing.

This is a fairly innocent class of authentication breach, but it should be fairly unnerving given the extent to which our lives and personal information are accessible. Anyway, these two stories led me to think about ways to both simplify the process of entering passcodes and passphrases while simultaneously hardening against some general attacks, in particular replay attacks (and to a lesser extent, man in the middle).

The premise is simple enough: As you're typing a password, letter by letter and stroke by stroke, each character is processed (either locally, or sent to a server). As soon as the authorization engine is comfortable with the amount of data provided, it sends a signal so that no more data is transmitted, and that authorization is complete.

In the same manner as the old MasterLock, maybe in a particularly auspicious occasion, one might only need one or two symbols in order to prove their identity. However, if the wrong digit is entered on the first try, the subsequent attempt must then obviously come with increased difficulty. Likewise, it may be advantageous to have a low initial difficulty if the login scenario seems very ordinary, which can be determined by any number of variables, including but not limited to the current IP Address, the location as determined by GPS or other means, stylometrics such as the rate and delay between typing individual letters, the number of simultaneous concurrent sessions, how the last session ended (by timeout or by an active logout). But an important part of the  system is that the difficulty has to be non-deterministic, because if we assume the attacker knows the system and can manipulate the variables at play, there is still a last vestige of hope that the attacker's first guess is wrong (after that the difficulty climbs and the attacker is no longer really a problem).

Note that the server would not specifically reveal that a password is incorrect (until it's manually submitted, like in existing systems). It would only indicate when the received content is sufficient.

In a keyboard input scenario, for a shell prompt or for generic password entry, it's probably important to keep the text box open until the user acknowledges that he has been authorized, however in case the connection has been compromised by a non-interactive eavesdropping man in the middle with the intent to replay the password, the client should stop sending additional letters as soon as the server signals that it's ok. This gives the server the option of never revealing to the user whether a response is sufficient, essentially forcing the user to enter the entire password and pressing submit.

Like how some safes or button pads have duress codes that silently call the police when triggered, there system could ignore invalid characters that prepend the actual password for entry, while subsequently blacklisting that given prefix and raising subsequent difficulty.

Of course this isn't a complete solution. There needs to be some segmentation of access based on current authorization levels. For instance, checking whatever new mail or facebook statuses exist probably does not warrant much authentication friction, but combing through old personal documents and emails, installing root software or changing system settings, should probably require higher levels. This can probably help in that by keeping a unified password of sorts for all levels, but isn't itself a complete solution. Two factor authentication is also important, in case a single device is compromised or some part of the scheme is untrusted.

I think it'd actually be pretty cool to see something like this implemented, because I think it might serve as a genuinely useful feature that enables a continuously variable spectrum that varies between when security is a situational necessity and when excessive user friction is detrimental.
