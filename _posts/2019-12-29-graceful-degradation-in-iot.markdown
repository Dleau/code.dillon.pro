---
layout: post
title:  "Graceful degradation for IoT"
date:   2020-05-16 00:00:00 -4000
categories: security
---

The IoT industry is plagued by poor security practices. Good security solutions are expensive, though devices are built cheaply to enter the evolving market quickly. Firmware updates that may address certain vulnerabilities are few and far between, even still proving difficult to implement for a typical home user. Red flags can be raised over intrusions, but appropriate, mitigating actions need to be taken swiftly and automatically.

My [MQP at WPI](https://www.wpi.edu/academics/undergraduate/major-qualifying-project) addressed these concerns and others. This project offered a solution that simutaneously maintained both conveinence of use and user privacy for IoT devices. My team proposed a novel, graceful degradation technique that modeled and handled network streams attributed to particular device functionalities. We intersected machine learning with network security to build a customizable application that offered fingerprinting, functionality recognition, and real-time network governance.

<p align="center">
  <img src="/assets/mqp/structure.png" style="zoom:30%;">
</p>

A Raspbian-based router harbored three important pillars: device fingerprinting, behavioral anomaly detection, and graceful degradation. [The Fingerbank API](https://api.fingerbank.org/devices), [nmap](https://nmap.org/), and [p0f](https://lcamtuf.coredump.cx/p0f3/) were used to identify and fingerprint IoT devices on the testbed wireless network. [Kitsune](https://github.com/ymirsky/Kitsune-py) was customized to serve as an IDS. Lastly, a completely novel degradation capability was built with Python atop [Scapy](https://scapy.net/) and [scikit-learn](https://scikit-learn.org/stable/index.html). 

<p align="center">
  <img src="/assets/mqp/filtering.png" style="zoom:30%;">
</p>

During brief, user-supervised intervals, classifiers were trained to recognize certain IoT device functionalities. Live stream traffic to or from a smart camera would be modeled. Traffic attributable to on/off commands for a smart plug or light bulb would be modeled. Armed with a slew of models, the degradation capability could attribute traffic to any one of a number of devices and functionalities in real-time. Additionally, and perhaps more importantly, the capability could restrict device functionalities at the first sign of intrusion when paired with Kitsune. 

A smart refrigerator should not be sending email. A smart camera should not be streaming to an arbitrary IP address twenty-four hours a day. This project not only raised red flags over intrusions, but enacted customized, network security policies in response. The solution we proposed performed favorably in over 90% of test cases involving network-based attacks.

This was but a synopsis of the project. If you're interested, you can access the complete report [here]({{ site.url }}/assets/iot_graceful_degradation.pdf).

