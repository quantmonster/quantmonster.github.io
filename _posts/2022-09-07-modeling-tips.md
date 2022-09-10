---
layout: post
title:  "Tips for Developing Valuable Models"
excerpt: "Stuff you don't find in math textbooks."
---

<h3>Focus on solving a problem that fits you.</h3>

A model's value is measured by how well it solves a problem. To solve a problem, you need

<ol>
<li>the ability to solve it, and</li>
<li>the persistence to stick with it throughout all the difficulties that will surely arise (otherwise the problem would already have been solved).</li>
</ol>

The ability to solve a problem is a combination of domain knowledge and technical expertise -- domain knowledge to envision a feasible solution, and technical expertise to make that vision a reality.

Persistence has a more emotional root -- doing something you love, wanting to fix something that angers you, a drive to conquer an opponent, etc. The more emotional connections you have to a problem, the easier it will be to stay motivated and persistent.

 
<h3>Start with the problem, not the model.</h3>

A model is worthless if it does not solve the desired problem. Even if it's elegant and theoretically interesting -- if it doesn't actually solve a problem, then it's worthless.

Now, I'm not suggesting to avoid elegant and theoretically interesting models. I'm just saying that these qualities shouldn't be considered at the beginning of the model development process. When you start building a model, the only thing on your mind should be the problem that the model is intended to solve -- because, again, if your model doesn't solve this problem, then it's worthless.

Of course, this approach may lead to convoluted models. That's intentional. If you have a convoluted model that actually solves a problem, then all you have to do is simplify it. This is generally much easier than the alternative, extending an elegant model that does not solve the problem.

As it turns out, models that are intentionally designed to solve solve specific real problems usually turn out to be theoretically interesting and fun to build. You can have a model that is both intellectually stimulating and a valuable solution to a real problem. But you need to start by solving a real problem. Real solutions naturally generate interesting theory, but it doesn't work the other way around.


<h3>Both you and your model need to understand the full context surrounding the problem.</h3>
<ul>
  <li>The first step to developing a model is to gather domain knowledge and fully grasp the context in which the model is meant to exist. If you skip this step, then your model might work in theory but probably not in real life.</li>
  <li>In order to gather domain knowledge, you need to engage in hands-on experience. So, avoid domains where you're averse to doing things manually and getting your hands dirty.</li>
  <li>A model can only be as good as the underlying data. If you want your model to do what an expert does, it needs to have all the information that an expert uses during their decision-making process. (Heard this one from Jason Roberts, who heard it from Peter Stone.)</li>
  <li>Once a model is detecting and leveraging most of signal in the data, it's higher ROI to improve the quality and breadth of data than to increase the algorithmic complexity of the model.</li> 
</ul>
 
<h3>Choose the right level for your first principles.</h3>
<ul>
 <li>It is often more efficient to manually encode expert knowledge in a structured data set and build a model on top of that, than to attempt to build a model that does everything from scratch.</li>
 <li>It's easy to rationalize that manually encoding expert knowledge takes too long. But if spending several weeks (or even months) creating a structured data set by hand will allow your model to accomplish important goals that it couldn't otherwise, then it's totally worth doing.</li>
 <li>Plus, when you have to manually encode expert knowledge, it means that you're creating highly relevant data that isn't publicly accessible. This gives you a major edge over any competitor who is not a domain expert or is unwilling to endure tedium for the sake of the model.</li>
</ul>

<h3>Get specific to your domain.</h3>
<ul>
 <li>In every domain there are insights that a domain expert would know from experience, that would likely evade a general-purpose algorithm. (This is not surprising, because general-purpose algorithms get their power of generality by reducing assumptions and focusing on the aspects of a problem that are conserved across domains.)</li>
 <li>By introducing domain-specific "shortcut" assumptions and considering relevant aspects of the problem that would otherwise be ignored, you can leverage your domain knowledge as a major advantage against competitors who do not have as much domain expertise.</li>
 <li>Domain expertise is to hard work as algorithmic aptitude is to talent. You can't increase your algorithmic aptitude by very much, but you can vastly increase your domain expertise by leaving the world of abstraction and getting concrete hands-on experience.</li>
 <li>Even after you become a domain expert, don't get cocky thinking you know everything there is to know within the domain. The amount of you know is still orders of magnitude less than the amount you don't, and the distribution of domain expertise among domain experts has a fat tail.</li>
 </ul>
 
<h3>Leverage your intuition and emotions.</h3>
<ul>
  <li>Routinely step back from the theory and implementation and observe your model's behavior. It needs to make sense intuitively and "feel" right emotionally. (If you've spent enough time building domain knowledge by doing things manually and getting your hands dirty, then you should have emotional reactions to the decisions the model makes.)</li>
  <li>The best machine learning model you have is your brain, and your brain only interfaces with interpretable computer models.</li>
  <li>The more linear and low-dimensional a model is, the easier it is to find good parameters using your intuition alone.</li>
  <li>Emotion is an essential part of the feedback loop for improving a model: 1) inspect the model's output, 2) produce a negative emotional reaction, 3) introspect your emotions to identify the root cause of the negativity, 4) describe what the output needs to look like order to produce a positive emotional reaction, 5) tweak the model to give the desired output, 6) return to step 1.</li>
</ul>
  
<h3>Make your model robust and reliable.</h3>
<ul>
 <li>Make your model robust to data issues (but make sure it logs a warning whenever it comes across a data issue). Data issues will happen from time to time, especially if the model is being developed in parallel with the underlying data infrastructure. The model can't just fall over and refuse to work whenever data issues happen.</li>
 <li>The more complex your model is, the more internal validation it needs. Depending on the severity and veracity of a failed sanity check, the model should either log a warning or throw an error, halt, and alert you.</li>
 <li>Unit tests are ideal, but if your model exists within a very complex system, then your unit tests won't cover all the possible edge cases no matter how hard you try. So internal and external validation become very important. (Internal validation = validating internal perceptions and decisions of model as it runs on real data in real time; external validation = validating that the model's sequence of output decisions over time on recent real data.)</li>
 <li>To gain confidence in your model and speed up the debugging process, it helps to generate human-readable justifications for why your model makes decisions it does.</li>
 <li>It's often worth investing some time to make your logs highly informative yet easy to skim. (Indents and empty line dividers are your friends.) Tuning and debugging go much faster if you can see the forest for the trees.</li>
</ul>

<h3>Refactor when appropriate.</h3>
<ul>
 <li>One goal of refactoring is to save you time in the long run. On one hand, you shouldn't refactor until you're reasonably confident that what you refactor is a permanent and essential part of the solution. On the other hand, you shouldn't wait so long to refactor that you experiencing lots of friction when trying to extend your solution.</li>
 <li>Another goal of refactoring is to enable other people to understand and modify your code. If you're going to hand off a piece of code to someone, then you should first refactor until it's reasonably clean.</li>
</ul>
 
<h3>Never stall out. (Corollary: Control the data-generating process.)</h3>
<ul>
 <li>Keep forward momentum. If a model is not producing a desired behavior and you're out of ideas, then temporarily hard-code the desired behavior as an "intervention," move on, and periodically revisit the intervention to try out more elegant ideas.</li>
 <li>If you don't control the data-generating process, then it becomes vastly more difficult (and sometimes impossible) to resolve data issues. You either need to own the data-generating process yourself or have trust, a good relationship, an open line of communication with the person who does.</li>
 <li>Don't embark on a project unless you have some solid ideas on how to approach it. If your desired outcome feels magical, then you probably don't (yet) have enough technical knowledge to achieve it.</li>
</ul>

<h3>Focus on high-ROI tasks.</h3>
<ul>
  <li>While it's good to keep developing technical expertise, returns are diminishing. However, you can always become orders of magnitude more productive by working on high-ROI tasks as opposed to low-ROI tasks.</li>
  <li>Even when you're working on a high-ROI task, you should periodically re-evaluate to make sure it's still high-ROI. Sometimes the act of working on a task reveals new information that indicates a more efficient way to accomplish the same goal.</li>
  <li>Know when to move on. If the completion of a task is measured on a scale from 0% (no work done) to 50% (low-quality solution) to 100% (absolute perfection), the ROI is often concentrated in the first 80%.</li>
  <li>Maintain a priority queue, not a to-do list. You'll never complete everything in your priority queue since the rate at which items are added will outnumber the rate at which items are completed. Therefore, it's essential to work on highest-priority items first.</li>
  <li>Strike a balance between shutting out distractions versus allowing yourself to think creatively about the future, so that you can keep a steady supply of high-ROI tasks.</li>
</ul>

<h3>If the goal is to "wow" users, then the model must clearly demonstrate its sophistication.</h3>
<ul>
  <li>Valuable models often work so elegantly and efficiently that they make extraordinarily difficult tasks seem easy. If the model does not demonstrate its sophistication, then users may not experience a "wow" moment, and they may even think that the model is wrong (since the complexity of the task is far beyond their perceived complexity of the model).</li>
  <li>To appreciate the sophistication of a model, users need to understand and be able to personally verify the what the model is doing at a high level. Consequently, it's necessary for the model to be very interpretable at a high level.</li>
  <li>Low-level implementation details should remain hidden since they do not matter to the user (and are often the "secret sauce" behind the model).</li>
  <li>Visualizations and animations are ideal because they give the user a clear picture of what is going on at a high level and can demonstrate complexity in an aesthetically pleasing way without overwhelming the user.</li>
</ul>