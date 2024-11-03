---
title: The Cyber Kill Chain
tags:
  - threat-intelligence
  - cybersecurity
description: An illustrated explanation of the Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains
---
During my pursuit to learn more about threat intelligence in the context of computer security, one paper — presented by many as being a hallmark of the subfield — came up so frequently that it was impossible to ignore. In this article, I would like to give my analysis and thoughts on the Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains, which was written by three information security professionals at Lockheed Martin: Eric Hutchins, Michael Cloppert, and Rohan Amin. Here, I am seeking to provide a simple explanation of the paper to help anyone struggling to grasp the idea of the cyber kill chain gain a deeper understanding. As someone who aids my learning by creating visuals, I will include some illustrations I made during my independent study.

# Advanced Persistent Threats

When we think about an attack on a computer system, we typically discuss the action of an attacker who exploits a vulnerability in a victim’s system. As technology has developed over time, we are seeing the emergence of attackers who conduct attacks that are larger in scale, using more sophisticated techniques, and with more targeted objectives. These attackers are known as **Advanced Persistent Threats** and many examples can be found in many different contexts. For example, Stuxnet is a computer worm supposedly created by the United States and Israel against Iran’s nuclear program. Stuxnet was strategically planned and executed, using thorough research and sophisticated techniques to accomplish its operation. An example mentioned in the paper are APTs who successfully exploited NASA and other government entities to steal rocket design information. This shows that APTs can perform attacks for a variety of different reasons but their level of sophistication is what sets them apart from other, more trivial attacks.

![](https://miro.medium.com/v2/resize:fit:1400/1*xB1CiUj13kblueDGRQCd3g.png)

Something that people fail to understand about threat actors is their human component. After all, APTs are human actors against computer systems. Moreover, APTs may have the same education as defensive professionals in cybersecurity or share the same degree of knowledge. While reading the book Sandworm A New Era of Cyberwar and the Hunt for the Kremlin’s Most Dangerous Hackers (a book that I highly recommend everyone to read to learn more about the current threat landscape), an analyst studying a zero-day attack — which was later attributed to actors working for the Russian military — marveled at the sheer human generosity behind the attack.

Here is a quote from the book:

> Erikson, the reverse engineer who first handled the zero-day in iSight’s black room, remembers his work disassembling and defusing the attack as a somewhat rare, fascinating, but utterly impersonal event…he’d analyzed thousands upon thousands of other malware samples and had learned to think of them as specimens for study without considering the author behind them — the human who had rigged together their devious machinery… But zero days do have authors… He was admiring the first hints of a remote, malevolent intelligence.

Threat actors are meant to be studied, and their nuances reflect the uniqueness of humans. One fault of humans, however, is that we are highly predictable, which is why it is so important to map out the cyber kill chain.

# Incident Response

Incident response refers to the processes an organization such as a government entity takes to investigate any threats and to attempt to prevent them in the future. Usually, incident response happens after compromise and focuses more on filling gaps that are identified through the process of vulnerability management. However, what is argued in this paper is that incident response should also focus on the threat actor themselves and not on simply fixing their actions post-compromise. By learning more about the specific adversary and the techniques they use during every phase of the kill chain (discussed later), defensive security teams can do a better job at defending their organization.

![](https://miro.medium.com/v2/resize:fit:1400/1*vynaHfQwXPKIRXeB-b6qwA.png)

# Indicators of Compromise

Before diving deep into the kill chain, it’s important to discuss the concept of indicators of compromise, which you may be familiar with if you have studied incident response before. An indicator of compromise is any sign that is a characteristic of an intrusion. In other words, it is a sign or “indication” that a system has been compromised. These could be IP addresses (atomic indicator of compromise), a hash value (computed indicator of compromise), or a combination of the two, which describes an attack (behavioral indicator of compromise). More information about indicators of compromise can be found [here](https://www.sans.org/blog/security-intelligence-attacking-the-cyber-kill-chain/).

Analysts need to track indicators of compromise as they are an integral part of understanding a threat so attacks can be properly detected and mitigated. The text describes the indicator life cycle states and transitions as follows:

1. Revealed: Analysts find indicators of compromise through study (i.e. malware analysis) or collaboration.
2. Mature: Use indicators of compromise when configuring defensive tools such as an intrusion detection system.
3. Utilized: When the indicators of compromise are seen, they are defended against through the aforementioned defensive tools.

![](https://miro.medium.com/v2/resize:fit:1400/1*j7k7hrzWJxf1Xmu2QSd3cA.png)

# The Kill Chain

Many phase-based models have already been created — many of which belong to the military context — which serve as inspiration or the breeding grounds for the cyber kill chain model. One of these models is the F2TEA kill chain process used by the United States Department of Defense Joint Staff, which includes the following stages for pursuing a specific target:​​ find, fix, track, target, engage, and assess.

Other models that are discussed in the text like the Mandiant model do not do an adequate job of considering measures of prevention of an attack in the earlier stages of the kill chain, which is part of the problem that these models have that the cyber kill chain hopes to avoid.

The main part of the article — of course — focuses on the cyber kill chain, which is composed of seven stages:

1. Reconnaissance: In this stage of the cyber kill chain, the threat actor chooses a target through research and attempts to learn as much as possible about them (for example, to establish attack vectors).
2. Weaponization: This stage is dedicated to developing or arming a payload delivered to the victim.
3. Delivery: Following weaponization, the attack sends the malicious payload to the victim.
4. Exploitation: This stage occurs when the payload is executed in the victim’s environment.
5. Installation: In this stage, the attacker succeeds in installing a payload or backdoor in the victim’s environment
6. Command and control: When a computer is compromised, a threat actor may want to connect it to a command and control server command and control server. A C2 server is used to send commands to the compromised system and can help the APT manage their attacks.
7. Actions on objectives: Advanced persistent threats are most likely attacking a system because they would like to fulfill a specific objective. During this stage of the cyber kill chain, the threat attacker accomplishes what they set out to do (i.e. data exfiltration).

![](https://miro.medium.com/v2/resize:fit:1400/1*DF1bqqJlLc_-O_lFXSoOjQ.png)

It is not enough to simply know about the cyber kill chain. In addition to learning about how threat actors operate, we must map the different stages of the kill chain to actionable defenses the organization can place. This is shown in the courses of Action Matrix below.

![](https://miro.medium.com/v2/resize:fit:1400/1*zywcs76G_eetOqd9OLXoNQ.png)

Here it becomes clear how this model differs from other similar models in threat intelligence as defenders are outlining the different phases of the cyber kill chain and identifying what technologies they can use to mitigate these attacks. It is noted that having all these defenses in their entirety is important because attackers usually will reuse the same strategies and tools they have in the past. This is because attackers have limited resources and using completely new strategies costs them time and money. From this reasoning, we can say that some zero-day attacks aren’t “zero-day” because they utilize the same tools as before but in a different stage of the cyber kill chain.

![](https://miro.medium.com/v2/resize:fit:1400/1*U-eBCqmSTfVsH65TsAiccQ.png)

Here is a quote from the article:

> In order for an intrusion to be economical, adversaries must re-use tools and infrastructure. By completely understanding an intrusion, and leveraging intelligence on these tools and infrastructure, defenders force an adversary to change every phase of their intuition in order to successfully achieve their goals in subsequent intrusions.

The article also discusses that an analyst must track the effectiveness over time of their defenses and see where they should prioritize their efforts (i.e., during what stage). It is stressed that analysts need to be able to study an attack in all its phases (even from the beginning stages, which is something that is often overlooked during intrusion analysis). Unsuccessful attacks still should be studied as any information gained about the APT is imperative for defenders to understand.

Campaigns refer to repeated attacks by a single threat actor. Campaigns can be somewhat of an advantage (though it’s hard to say that any attack is an advantage) because patterns are more obvious and can be relied on over the long term. By studying their patterns and common indicators of compromise between intrusion events, defenders can better predict what may occur in the future.

What defenders are trying to do is gather as much information as they can about an attacker including their objectives and tactics, techniques, and procedures or TTPs. Teams may give a threat actor a name like Nomadic Octopus, but this is only to help keep track of the threat actor and “give a name to a face”. What they want to do is peel back the various layers in their metaphorical onion and learn more about how they function (their TTPs) and what makes them tick (their intent).

![](https://miro.medium.com/v2/resize:fit:1400/1*mBfJeBcfJmP2hmjA_-TMPg.png)

(As a side note, if you’re curious about the naming conventions of these threat actors, I found [this](https://threatpost.com/the-apt-name-game-how-grim-threat-actors-get-goofy-monikers/141445/) fun read.)

# Final Thoughts

The cyber kill chain is a concept that has come up repeatedly during conversations I have had with security professionals, as well as in my independent study. It was thus beneficial for me to go through the entirety of the paper and I implore all students to do the same. The cyber kill chain provides a model for analysts to use when analyzing threats in their organizations and brings them one step closer to preventing future incidents. As mentioned, APTs are simply humans with faults and behavioral patterns. When defenders identify these qualities, they will be better prepared to handle whatever comes their way.

# Sources

1. Hutchins, Eric M., Michael J. Cloppert, and Rohan M. Amin. _Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains_. Lockheed Martin Corporation, 2011, [www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf](http://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf).
2. Greenberg, Andy. _Sandworm: A New Era of Cyberwar and the Hunt for the Kremlin’s Most Dangerous Hackers_. Anchor Books, 2020.