---
layout: post
title:  "Quants vs Systems Coders (In Progress)"
excerpt: "Two subtypes of coders."
---

While developing and teaching a super-advanced high school applied math/CS <a href="https://www.eurisko.us/" target="_blank">sequence</a> over the course of several years, a trend emerged that each student would eventually grow to exhibit one of two different attitudes towards coding. [1]

In one group were the <b>systems coders</b>, who were drawn to developing tangible systems that they could interact with in "cool" ways. They loved adding new features to our implementation of the game <i>Space Empires</i>, as well as making the UI look aesthetically pleasing. They enjoyed developing autonomous AI players for games but would tend to take a brittle case-based approach with an overwhelming number of cases. They didn't particularly enjoy algorithms assignments and would sometimes attempt to implement algorithms before actually understanding how they work. While debugging, they would often waste time making superficial changes to their code instead of taking the time to gain a deeper understanding of the issue.

In the other group were the <b>quants</b>, who were drawn to developing algorithms that compressed wild jungles of complexity into compact, elegant, generalizable implementations. Their autonomous AI players would be theoretically simple yet highly effective. They loved algorithms assignments. But they were apathetic about adding new features to our game implementation and would often try to offload responsibilities onto others. They would often be resistant to tinkering while debugging, and would often waste time operating under the false assumption that the logic in their head is exactly equivalent to the logic that they've actually implemented.

To keep both groups happy, we alternated "quant" and "systems" weeks. During quant weeks, we would focus on quant-themed tasks like implementing machine learning algorithms and (afterwards) reproducing academic research papers in AI. During systems weeks, we would press forward with implementing <i>Space Empires</i>. Each week, half the class would celebrate and the other half would groan. [2]

Interestingly, though, the groans would be disproportionately louder during systems week. The quants hated systems week way more than the systems coders hated quant week.

The systems coders didn't really enjoy quant assignments, but as long as the quant problems were concrete and hands-on, the systems coders didn't complain too much. Getting a systems coder to do a quant assignment was like trying to get a kid to eat their vegetables. If you present the vegetables in an enticing way and promise dessert afterwards (but only if they eat the vegetables), it usually works out.

But getting a quant to participate in collaborative systems development was far more difficult. In the best case, they would try to get away with doing as little work as possible. In the worst case, they would argue that <i>Space Empires</i> was tedious and did not have educational value. 

After some trial and error, we eventually settled into a systems development rhythm that satisfied the quants and leveraged the respective strengths of the systems coders and quants. The systems coders, who were chomping at the bit to add more features and complexity, would be allowed to do so -- but before actually implementing anything, they would have to critically analyze the tradeoffs of the myriad possibilities and get the rest of their team's buy-in on what they were going to implement. If the feature involved any algorithmic complexity that could be isolated into a single component, they would hand the development of that component off to the quants. Otherwise, the quants would work on developing autonomous AI players for the existing version of the game, and as new features were introduced, the quants would extend their autonomous players to exercise and test the new features.

<h2>Notes</h2>

[1] Technically it was a spectrum. There was a minority of students who had a mix of characteristics from the different groups. But even those students leaned significantly further towards one group as opposed to the other.

[2] The ratio of systems coders to quants wasn't actually 1:1. It was more like 1:2, or even 1:3. However, my classes were likely a biased sample since they were drawn from students who were already in <a href="https://www.mathacademy.us/" target="_blank">Math Academy</a> to begin with.
