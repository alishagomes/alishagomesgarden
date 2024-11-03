---
title: Diamond Model of Intrusion Analysis
tags:
  - threat-intelligence
  - cybersecurity
description: My thoughts and analysis of the diamond model of intrusion analysis and its greater role in the field of threat intelligence
---
I am a fiend for “a-ha” moments during study. Recently, I had many of these moments while studying the diamond model of intrusion analysis. Not only because I found the model to be incredibly intuitive in its design and implementation, but also because I was able to draw clear connections between it and what I had learned previously in my threat intelligence learning journey (i.e. the [[The Cyber Kill Chain]]). I share some of my notes from this sixty-page paper here. What I seek to do in this post (and in all of my posts) is to give a summary of something I consumed in my understanding. I hope to provide other students with this paper with a clearer grasp of the subject. Truthfully some of the concepts presented in this paper are difficult to visualize, but — caution — once you understand them, you may feel like you can stop any adversary in their tracks.

Before proceeding, please read the full paper [here](https://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf).

The diamond model of intrusion analysis seeks to provide analysts with a model they can use to adopt a scientific approach while analyzing an intrusion. This model connects well with other models in the threat intelligence space like the [[The Cyber Kill Chain]], as well as MITRE’s ATT&CK. Instead of just mitigating one intrusion (defeating an attack), it seeks to mitigate all of the adversary’s actions (defeating the adversary). It helps analysts to see the “bigger picture” of an attack and allows for the creation of hypotheses that are supported by evidence, which may predict what an adversary may do next. With this model, we are learning more about the adversary. Moreover, it helps to achieve our greater purpose of preventing all further intrusions.

An event is a single component in a series of steps the adversary takes towards their objective. This is where the [[The Cyber Kill Chain]] comes into play as these events are ordered into phases (as a reminder these are reconnaissance, weaponization, delivery, exploitation, installation, command and control, and actions on objectives). As the name suggests, the diamond model has four major components or core features. The core features are linked together, which helps analysts pivot from one feature to another (like following breadcrumbs) to gain more information about an event. The core features are adversary, capability, infrastructure, and victim. These are covered in more detail here:

- **Adversary:** The adversary is an individual or group who is the source of an event and wants to achieve a particular objective by exploiting a vulnerability in a victim’s computer system. The adversary can be broken down into the adversary operator and the adversary customer. The adversary operator is the person performing the attack (for example, someone who develops the specific exploit used) and the adversary customer is someone who uses the services provided by the operators (you can think of them as the client).
- **Capability:** The capability is what is used during the event. This could include the tools or resources they have in their arsenal to execute their attack. You can think of these as the tactics, techniques, and procedures (TTPs), which references MITRE’s ATT&CK framework. An example of this is the ransomware used during an attack.
- **Infrastructure:** This feature describes the organizational structures or resources that are needed to fulfill the operations of the adversary. This can include the servers that host malicious files or command and control (C2) servers.
- **Victim:** The victim is the individual or group that the adversary is attempting to attack. The victim contains the victim persona (their identity) and the victim asset (the specific attack surface).

There are also meta-features that further describe the event such as timestamp (date and time of an event), the phase of the event (in the [[The Cyber Kill Chain]]), the result (whether the event was successful, a failure, or unknown), direction (the movement of events where the origin and destination of the event may differ), methodology (describes the class of the attack), and resources (the necessary elements that are required in an attack).

The diamond model can become more complex when you consider the relationship between different axes. In the vertical axis, connecting the adversary and the victim is the social-political feature. The authors describe the inherent link between the adversary and the victim. By understanding this relationship, the analyst can hypothesize about an adversary’s intent.Adversaries can have varying degrees of persistence (where an adversary pursues a victim for an extended period). Adversaries who endure the journey of attacking a victim are known as persistent adversaries. Some important details that should be considered in determining why an adversary is persistent include (1) the adversary’s cost and (2) the effort needed to continue to attack the victim. We must question what is so special about a victim. Why does an adversary pursue a victim even when the risk of pursuing them becomes high? Questioning why a victim was chosen by an adversary — and why they may be particularly persistent in pursuing them — may help analysts figure out ways to decrease the potential utility received by the adversary in pursuing the victim by lowering the attractiveness of a victim or by increasing the risks in pursuing the victim.

On the horizontal axis, connecting the infrastructure and capability is the technology feature. This extension is the relationship between the capability and infrastructure. It attempts to further understand the technology utilized by the adversary, which enables the infrastructure and the capabilities they use.

Pivoting is a strategy that helps analysts move from one core feature in the diamond model to another (which is where the lines that connect each of the vertices in the diamond model come into play). Pivoting is like following breadcrumbs — where one piece of evidence leads to another. You are uncovering more information about an event. It also aids in hypothesis testing. By understanding how the different vertices in the diamond model relate to one another, an analyst begins to learn more about the adversary, which helps predict other activities they perform.

Analysts can also adopt different approaches that focus on one element of the diamond model. This is covered in the Centered Approaches section and helps an analyst gain more information about an intrusion. For example, a capability-centered approach focuses on the capabilities used in events and can point towards other capabilities and help to connect adversaries in different incidents. The paper brings up how “Red October” was reverse malwared to find the capabilities used in the attack, which helped to find other victims and potentially attribute the adversary based on what victims they were targeting.

The activity trend is where things may get a little tricky (it took me more than a couple of rereads to understand this part), but the general idea is that events are not isolated occurrences. Rather they operate in sequences (which can be created when causal relationships are studied) that make up a single trend. Relationships between events in different trends can then be drawn.

Activity trends enhance the typical understanding of attack graphs. This is described by the authors as being “an enumeration of all possible paths an adversary may take to penetrate computer networks achieving their desired intent.” What creating an activity trend does is allow you to apply real data to inform yourself about the behaviors of the adversary.

Here I will attempt to break this down further:

- First, events are grouped into phases using the [[The Cyber Kill Chain]]. A vertical trend is created by creating a sequence of these events. This may require additional research by the analyst as all the information about a specific incident may not be known so getting additional data and conducting thorough analysis is needed. This trend represents one adversary-victim pair.
- Multiple threads are created for different adversary-victim pairs and these trends can be placed one after the other.
- A horizontal correlation can be drawn that links events in different activity threads. This is beneficial because one vertical tread can help fill gaps in another trend. This will also help in activity groups (discussed in the next section).

There are more nuances to activity trends than I am describing here but I hope to paint a general idea of this concept. I implore anyone curious to learn more about the intricacies of the activity trend by reading the article in its entirety.

Creating these trends enables the analyst to develop hypotheses that can be tested and supported. Moreover, organizing adversary activities and identifying these vertical threads and horizontal linkages helps to illustrate the adversary process, answering the “how” of how an adversary accomplished their activity.

An activity-attack graph is a way to visualize and combine the intelligence of activity threads and attack graphs. As stated by the authors, “Attack graphs identify and enumerate paths an adversary could take while activity threads define the paths an adversary has taken. These can exist together by overlaying activity threads on top of a traditional attack graph. We refer to this intelligence-informed attack graph as an activity-attack graph.”

This allows analysts to use their understanding of current events and trends to predict potential paths the adversary can take. This is valuable from a defensive perspective as it lets the defender be ahead of the adversary and implement any measures that can counter the adversaries predicted actions.

Activity Groups are a collection of similar individual events and activity trends. This helps to define for many reasons including identifying and attributing adversary campaigns and to see the evolution of activity over a specific time frame. The process for creating these groups is as follows:

1. **Analytic Problem:** Define a problem statement that you would like to answer. Questions such as “how has an adversary’s activity changed over time”, “what is the current vector to infer future change?”, “which capabilities show evidence of common authors/developers?”, and “which resources and processes are the most common and critical to an activity and/or campaign?” are only a few of the included questions in the text.
2. **Feature selection:** Choose the features for grouping events and trends.
3. **Creation:** This step refers to the creation of activity groups based on the selected features.
4. **Growth:** When events and activity trends are discovered, organize them into groups.
5. **Analysis:** This refers to the analysis of the groups to help answer the analytic problem.
6. **Redefinition:** Over time, new data may be gathered that requires the adjustment of groups.

An important note to make about creating these groups is to avoid creating these groups by attribution (by the particular adversary). Here is a quote from Sergio Caltagirone, one of the authors of the paper, during a talk he gave with another co-author Andy Pendergast for a ThreatConnect webinar.

This is from [The Diamond Model: An Analyst’s Best Friend](https://www.youtube.com/watch?v=TE6UY3u9aEY&t=41s).

> There are a lot of times when two groups or three groups or even more will work together for a common cause…and the thing that really screws a lot of people up is that if you’re going by attribution but you’ve got multiple countries working against you you’re not going to group very well…You’ve just messed up your grouping function because you’re not grouping accurately and the reason you’re doing that is because you’re effectively guessing at attribution rather than actually having data — Sergio Caltagirone

Activity groups can then be ordered hierarchically into activity group families (though this is more relevant for larger enterprises and will not be covered here.)

Finally, the ‘Planning and Gaming’ section emphasizes the role of the diamond model to support the decision-making of defenders. Analysts need to use the model to study their adversaries, think about the costs associated with any defensive measures they take, and ultimately make strategic decisions about what to do with the information they gather.

# Final Thoughts

The diamond model presents yet another model that adds to an analyst’s toolkit during intrusion analysis. It maps well with other models in threat intelligence such as MITRE’S ATT&CK and the [[The Cyber Kill Chain]] and is something that every analyst should add to their toolkit. The diamond model breaks down adversarial operations into four key components: adversary, infrastructure, victim, and capability. By studying the relationships between these components, analysts can use contextual intelligence to proactively counter adversarial threats and strengthen their security posture.

# References

- Caltagirone, Sergio, Andrew Pendergast, and Christopher Betz. _The Diamond Model of Intrusion Analysis_. Center for Cyber Intelligence Analysis and Threat Research, 2013.
- “The Diamond Model: An Analyst’s Best Friend.” [_Www.youtube.com_,](http://www.youtube.com,/)[www.youtube.com/watch?v=TE6UY3u9aEY.](http://www.youtube.com/watch?v=TE6UY3u9aEY.) Accessed 26 May 2023.