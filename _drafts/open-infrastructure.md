---
published: false
title: Open Infrastructure
layout: post
tags: []
---

## My New Ops Job

Next week, I&rsquo;m starting work as the only DevOps Engineer on the Mozilla Research team. While I&rsquo;ve held a variety of superficially similar jobs in the past few years, this one offers a special opportunity to apply the values I appreciate as a software developer to the infrastructure design and maintenance which represents my work as an ops guy.

## Wait, what&rsquo;s DevOps?

Many of the operations engineers whom I look up to regard the term &ldquo;DevOps&rdquo; as an absurd buzzword. I share their antipathy toward its use alongside &ldquo;cloud&rdquo; to mean some mysterious panacea of modernization, often spouted by the same technologically illiterate individuals who&rsquo;d assume a hypervisor to be some sort of new-and-improved sunshade.

Although it could do with a less abused name, the modern systems administration skills that companies are seeking when they open a job req for &ldquo;DevOps Engineer&rdquo; deserve to be differentiated from &ldquo;old-school operations&rdquo;.

In my opinion, the most useful meaning of &ldquo;DevOps&rdquo; is to describe to the paradigm in which infrastructure is code. In this sense, the operations team are necessarily developers, since their main goal is to write code which describes the tasks that they would have had to do manually in the olden days. This change of perspective encourages a &ldquo;DevOps&rdquo; team to apply best practices which were unattainable back when every server was a special snowflake: Testing, deployment automation, version control of configurations, and code review, to name only a few examples.

There are those who use the vagueness of &ldquo;DevOps&rdquo; to justify asking one person (or group) to perform the roles of an entire development team and an entire operations team simultaneously. This could concievably have some benefits, such as improved communication between teams, but it mostly misses the point. I&rsquo;ve talked to many of my peers unfortunate enough to end up in the misguided type of &ldquo;DevOps&rdquo; role, and learned that they tend to spend about 90% of their time with one of the two hats on and only switch to the other when they have to.

## So, Infrastructure is Code...

Yes! And that&rsquo;s where it all gets interesting. Mozilla&rsquo;s values of openness and the Research team&rsquo;s experimental nature mean that the code I&rsquo;ll write to solve infrastructure problems has no secrets in its design. There are a handful of necessary secrets related to our instantiation of the code, such as the AWS credentials of accounts whose bill Mozilla pays, but they don&rsquo;t have nearly the crippling impact on openness that a design secret would.

At a typical software company, enabling anyone else to precisely duplicate your product is a Really Bad Idea (TM). Any company that sells software has to have some secrets &ndash; people won&rsquo;t usually pay for code that they could get for free. There are a few software-related companies which appear to operate quite profitably without secrets, but examine them more closely and you&rsquo;ll find that they&rsquo;re actually selling a service like support. When a company has some secret in their code&rsquo;s design, concern for protecting it trickles down and metamorphoses into concern for hiding the details of the infrastructure necessary to deploy the code as well.

If you debunk the illusion that sharing their infrastructure will harm the company, operations teams are still extremely reluctant to share their code with others. The typical excuse for opening only a choice library or two, rather than the entire ops codebase, is embarrassment at its quality. Cloaked in the altruistic guise of &ldquo;I don&rsquo;t think our code would help anyone else, and might lead them astray&rdquo;, the underlying sentiment is one of regret that a given infrastructure project never met those lofty criteria to which its authors aspired. It&rsquo;s the same psychological effect that discourages amateur artists &ndash; we gain the ability to recognize good art (or code) more quickly than the ability to produce it ourselves. And in the case of ops, we often ship code which works but could be greatly improved if only more time was available. Publicly sharing work that one knows was only &ldquo;good enough&rdquo; is scary and embarrassing, and I don&rsquo;t fault people for their reluctance to do it.

## ...So we should be sharing it!

At least, I think so. I think it&rsquo;s rare and wonderful to have an important infrastructure project with no reason to keep its code secret, and I have hoped from the beginning that whoever gets this Mozilla Research DevOps Engineer job will take advantage of the opportunity. It&rsquo;s entirely a selfish wish, and I have it because I find myself teaching devops concepts to newbies a lot and wanting some really good, real-world repositories to point them at as examples. I was pretty outspoken about these opinions throughout the interview process, so I can only conclude that the team which decided to hire me concurrs.

To recap, being Mozilla Research&rsquo;s very own in-house &ldquo;DevOps&rdquo; Engineer is a unicorn of a job because it has cleared the first hurdle that prevents infrastructure-as-code from being open source, and has a running start and a tailwind toward the second. The challenge we&rsquo;ve already overcome is that of design secrets, critical company information which would be leaked by sharing even a sanitized version of the infrastructure, and we&rsquo;ve overcome it by not having any. The major remaining challenge is that publishing work done in a hurry is scary, because it might be bad and might make me look bad to have it out there with my name on it.

## If We Build It, Will They Come?

That is, in my opinion, the hardest question of all. If I publish the infrastructure that I&rsquo;m building in real time, warts and all, will anyone benefit?

If the infrastructure works at all, and includes sufficient documentation for anyone to set up their own instance of it if they so desire, then students wishing to learn about &ldquo;DevOps&rdquo; in the real world have already benefitted.

Selfishly, though, I&rsquo;d like to get some contributions back. In my experience with the kinds of code that do and don&rsquo;t get contributors, here are some factors which I think will be important to gaining contributions from people who aren&rsquo;t me:

Relevance. Mozilla Research is a great place to be for this, because Rust is a shiny new programming language with quite a bit of attention on it, so the code that describes its continuous integration and hosting is likely to be of interest to people experimenting with it. Prestige. People want to get commits into a project that their peers and prospective employers have heard about. With the right promotion, the build infrastructure for Rust and Servo piggyback on the projects&rsquo; fame. Prove Someone Wrong. If I offer the infrastructure as a canonical example of how to correctly use the tools it&rsquo;s built on, I will offend and anger the power users and authors of those tools, and they will very likely point out many places where my code needs improvement. Sufficient repetitions of this cycle should cause the code to converge into a state which both works and appears to be a good example of how to use the tools. If it&rsquo;s offered as a real-world example in the tools&rsquo; tutorials and documentation, that puts a bunch of newbie eyes on the code, and the resulting questions are a great way to identify additional areas for improvement. So in the best case I&rsquo;ll get a bunch of help and advice. In the worse case, where everyone totally ignores it, I&rsquo;ll still be better off because the imagined public eye will push me to document my decisions better and adhere to higher standards of code quality.