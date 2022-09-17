---
layout: post
title:  "(In Progress) Tips for Developing Valuable Models"
excerpt: "Stuff you don't find in math textbooks."
---

<h2>At A Glance</h2>

<b>The Problem -</b> Focus on solving a problem that fits you. Start with the problem, not the model. Make sure you understand the problem in reality, not just in theory.

<b>The Data -</b> Your model can only be as good as its underlying data. Don't be afraid to encode domain knowledge manually.

<b>The Development Process -</b> Leverage your emotions. Make your model justify its own decisions. Invest in high-quality logs. Hard-code interventions when necessary. Focus on high-ROI tasks.

<b>Stabilizing the Model -</b> Validate the model's perceptions and decisions. Don't get derailed by minor data issues. Refactor when appropriate.

<b>Showcasing the Model -</b> If the goal is to "wow" users, then the model must clearly demonstrate its sophistication.

<h2>The Problem</h2>

<h4><b>Focus on solving a problem that fits you.</b></h4>

A model's value is measured by how well it solves a problem. To solve a problem, you need

<ol>
<li>the ability to solve it, and</li>
<li>the persistence to stick with it throughout all the difficulties that will surely arise (otherwise the problem would already have been solved).</li>
</ol>

The ability to solve a problem is a combination of domain knowledge and technical expertise -- domain knowledge to envision a feasible solution, and technical expertise to make that vision a reality.

Persistence has a more emotional root, e.g. doing something you love or fixing something that angers you. The greater the variety and strength of emotional connection you have with a problem, the easier it will be to stay motivated and persistent.
 
<h4><b>Start with the problem, not the model.</b></h4>

A model is worthless if it does not solve the desired problem. Even if it's elegant and theoretically interesting -- if it doesn't actually solve a problem, then it's worthless.

Now, I'm not suggesting to avoid elegant and theoretically interesting models. I'm just saying that these qualities shouldn't be considered at the beginning of the model development process. When you start building a model, the only thing on your mind should be the problem that the model is intended to solve -- because, again, if your model doesn't solve this problem, then it's worthless.

Of course, this approach may lead to convoluted models. That's intentional. If you have a convoluted model that actually solves a problem, then all you have to do is simplify it. This is generally much easier than the alternative, extending an elegant model that does not solve the problem.

As it turns out, models that are intentionally designed to solve solve specific real problems usually turn out to be theoretically interesting and fun to build. You can have a model that is both intellectually stimulating and a valuable solution to a real problem. But you need to start by solving a real problem. Real solutions naturally generate interesting theory, but it doesn't work the other way around.


<h4><b>Make sure you understand the problem in reality, not just in theory.</b></h4>

It's possible to convince yourself that you're starting with the problem, when you're actually not.

If you don't have hands-on experience with all facets of the problem, then you'll probably make lots of assumptions that are plausible but false. If this is the case, then you won't actually be solving the problem that you think you're solving.

This leads to the ultimate deathtrap: a model that works in theory but not in reality. A model that despite being elegant, intuitive, and the product of countless hours of work, is ultimately worthless because it doesn't solve the problem that it needs to solve.

Below are two strategies that you can use to avoid this tragic fate.

<ol>
<li>Gather hands-on experience and domain knowledge before beginning the modeling process. (As a corollary, avoid domains where you're averse to doing things manually and getting your hands dirty.)</li>
<li>As soon as you think your model solves the problem well enough to be useful, test it out in the real world to ensure that reality matches up with your expectations. Don't spend time refactoring and optimizing until you know it's worthwhile to do so.</li>
</ol>

<h2>The Data</h2>

<h4><b>Your model can only be as good as its underlying data.</b></h4>

The saying "crap in, crap out" is cliche for a reason. If you want your model to do what a human expert does, then it needs to have access to all the information that the human uses during their decision-making process (and this information needs to be correct). [1]

Two corollaries follow:

<ol>
<li>Once a model is detecting and leveraging most of signal in the data, improving the quality and breadth of the data will result in higher ROI than increasing the algorithmic complexity of the model.</li>
<li>It's important to control the data-generating process. If you don't, then it becomes vastly more difficult (and sometimes impossible) to resolve data issues. You either need to own the data-generating process yourself or have a good relationship with the person who does.</li>
</ol>

<h4><b>Don't be afraid to encode domain knowledge manually.</b></h4>

It's easy to rationalize that manually encoding domain knowledge takes too long, so your model must learn everything on its own from scratch.

In these situations, it's important to ask yourself: "If my model manages to learn everything from scratch, would that be groundbreaking enough to publish in a high-impact journal?"

If the answer is yes, and you're not actually an academic whose very definition of success is to publish models that learn from scratch, then stop right there. Research projects like this take many months if not years to fully pan out, and there is no guarantee of success.

If you can manually encode the domain knowledge you need in a matter of weeks or months, then it's a no-brainer that you should do that instead. It may feel tedious, but you'll lower your risk of failure while simultaneously increasing your development velocity.

At its best, manually encoding domain knowledge can allow you to bypass insurmountably difficult problems, and you can leverage this as a major advantage against competitors who do not have as much domain expertise as you do.

That being said, it would also clearly be a mistake to spend time encoding domain knowledge that your model can easily infer on its own. Only encode domain knowledge manually when doing so allows your model to bypass a publication-caliber problem.


<h2>The Development Process</h2>
 
<h4><b>Leverage your emotions.</b></h4>

Quants are often portrayed as unfeeling robots who medalled in the International Math Olympiad in high school and haven't thought about anything but numbers since.

However, even if they don't show it outwardly, the ideal quant will experience lots of emotions during the modeling process and leverage them to improve the model.

The idea is to routinely step back from the theory and implementation and observe your model's behavior. It needs to not only make sense intuitively but also "feel" right emotionally. (If you've spent enough time building domain knowledge by doing things manually and getting your hands dirty, then you should have emotional reactions to the decisions the model makes.)

Emotion is an essential part of the following feedback loop for improving a model: 

<ol>
<li>Inspect the model's output.</li>
<li>Produce a negative emotional reaction.</li>
<li>Introspect your emotions to identify the root cause of the negativity.</li>
<li>Describe what the output needs to look like order to produce a positive emotional reaction.</li>
<li>Tweak the model to give the desired output.</li>
<li>Return to step 1.</li>
</ol>

<h4><b>Make your model justify its decisions.</b></h4>

A properly justified decision will not only contain a precise description of the decision, but also reference key quantities or factors that led to the decision.

If you have your model justify its decisions, you'll benefit in at least three ways:

<ol>
<li><i>The logic will become more robust.</i> The act of justifying a decision requires you to think through your reasoning very carefully and tighten up any areas of ambiguity.</li>
<li><i>Debugging will go much faster.</i> The justifications will remind you of the decision logic and provide snapshots of the key quantities right off the bat, without you needing to inspect any code.</li>
<li><i>It will be easier to react emotionally to the model output.</i> As described in the previous tip, emotion is an essential part of the feedback loop for improving a model.</li>
</ol>

<h4><b>Invest in high-quality logs.</b></h4>

It's often worth investing some time to make your logs highly informative yet easy to skim.

When you can quickly skim through rich information about the model's behavior, you can quickly

<ol>
<li>determine whether the behavior looks reasonable or not,</li>
<li>identify any issues that are occurring,</li>
<li>identify surroundings that are implicated in the issues, and</li>
<li>develop hypotheses about what is going on or where you need to investigate further.</li>
</ol>

In other words, high-quality logs can help link the "big picture" model behavior to the specific details from which it arises.

<h4><b>Hard-code interventions when necessary.</b></h4>
<ul>
 <li>Keep forward momentum. If a model is not producing a desired behavior and you're out of ideas, then temporarily hard-code the desired behavior as an "intervention," move on, and periodically revisit the intervention to try out more elegant ideas.</li>
 <li>Don't embark on a project unless you have some solid ideas on how to approach it. If your desired outcome feels magical, then you probably don't (yet) have enough technical knowledge to achieve it.</li>
</ul>

<h4><b>Focus on high-ROI tasks.</b></h4>
<ul>
  <li>While it's good to keep developing technical expertise, returns are diminishing. However, you can always become orders of magnitude more productive by working on high-ROI tasks as opposed to low-ROI tasks.</li>
  <li>Even when you're working on a high-ROI task, you should periodically re-evaluate to make sure it's still high-ROI. Sometimes the act of working on a task reveals new information that indicates a more efficient way to accomplish the same goal.</li>
  <li>Know when to move on. If the completion of a task is measured on a scale from 0% (no work done) to 50% (low-quality solution) to 100% (absolute perfection), the ROI is often concentrated in the first 80%.</li>
  <li>Maintain a priority queue, not a to-do list. You'll never complete everything in your priority queue since the rate at which items are added will outnumber the rate at which items are completed. Therefore, it's essential to work on highest-priority items first.</li>
  <li>Strike a balance between shutting out distractions versus allowing yourself to think creatively about the future, so that you can keep a steady supply of high-ROI tasks.</li>
</ul>


<h2>Stabilizing the Model</h2>
  
<h4><b>Validate the model's perceptions and decisions.</b></h4>

If your model exists within a very complex system, then no matter how hard you try, unit tests won't cover all the possible edge cases. So, validation becomes very important.

There are two general categories of validation that I've found useful:

<ul>
<li><i>Immediate validation:</i> validating the model's internal perceptions and decisions at the moment that they occur.</li>
<li><i>Retrospective validation:</i> validating the model's sequence of output decisions over time to make sure that it's achieving the desired long-term behavior.</li>
</ul>

The more complex your model is, the more validation it needs. Depending on the severity and veracity of a failed validation check, the model should either log a warning or throw an error, halt, and alert you.


<h4><b>Don't get derailed by minor data issues.</b></h4>

Minor data issues will happen from time to time, especially if the model is being developed in parallel with the underlying data infrastructure.

But if the model has end-users, the it can't just fall over and refuse to work whenever a minor data issue occurs. If you as a human can infer what to do in the event of a minor data issue, then that same logic needs to be built into the model.

That being said, even if the model manages to handle a minor data issue, it should still log a warning. It's a good idea to sort out those issues eventually (or at least be aware of them). It's just a really, really bad idea to make your end-users wait for you to do so.

<h4><b>Refactor when appropriate.</b></h4>
<ul>
 <li>One goal of refactoring is to save you time in the long run. On one hand, you shouldn't refactor until you're reasonably confident that what you refactor is a permanent and essential part of the solution. On the other hand, you shouldn't wait so long to refactor that you experiencing lots of friction when trying to extend your solution.</li>
 <li>Another goal of refactoring is to enable other people to understand and modify your code. If you're going to hand off a piece of code to someone, then you should first refactor until it's reasonably clean.</li>
</ul>


<h2>Showcasing the Model</h2>

<h4><b>If the goal is to "wow" users, then the model must clearly demonstrate its sophistication.</b></h4>
<ul>
  <li>Valuable models often work so elegantly and efficiently that they make extraordinarily difficult tasks seem easy. If the model does not demonstrate its sophistication, then users may not experience a "wow" moment, and they may even think that the model is wrong (since the complexity of the task is far beyond their perceived complexity of the model).</li>
  <li>To appreciate the sophistication of a model, users need to understand and be able to personally verify the what the model is doing at a high level. Consequently, it's necessary for the model to be very interpretable at a high level.</li>
  <li>Low-level implementation details should remain hidden since they do not matter to the user (and are often the "secret sauce" behind the model).</li>
  <li>Visualizations and animations are ideal because they give the user a clear picture of what is going on at a high level and can demonstrate complexity in an aesthetically pleasing way without overwhelming the user.</li>
</ul>

<h2>Notes</h2>

[1] I heard the phrasing <i>"if you want it to do what a human does, then it needs to have all the information that a human does"</i> from Jason Roberts, who recalls hearing it from Peter Stone in the context of soccer-playing robots.