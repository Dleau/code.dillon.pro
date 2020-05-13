---
layout: post
title:  "Building a Raspbian rootkit"
date:   2020-02-16 23:30:00 -4000
categories: security 
---

![Malicious ps build omits display of a process]({{ site.url }}/assets/rootkit_ps.png)

Many APTs leverage [rootkits](https://en.wikipedia.org/wiki/Rootkit) to obfuscate malicious files and processes on compromised machines. The detection and removal of a rootkit can be arduous even for security experts. I downloaded [procps source](https://gitlab.com/procps-ng/procps), injected code to obfuscate certain, running Python processes, and deployed a malicious build of the `ps` tool on a Raspberry Pi. The image above shows a malicious build of `ps` omitting display of a "malicious" Python process. From there, `sudo rm /bin/ps && sudo mv ./ps/pscommand /bin/ps` would replace a normally functioning `ps` with my adversarial `ps`. 
