
### Unlikely Code Prediction
#### _Due date: 11/20/2017_

Automate software development security by mining code changes over time to
extract signs that indicate the introduction of a vulnerability, either through
malice or accident.

#### Abstract

The world is being rebuilt in code. Therefore, it needs safeguards against
malicious code purposely inserted by adversaries to create new security
vulnerabilities in it. Hiring security experts to deal with this problem used to
be the province of tech companies, but, these days, almost every organization is
a tech company. City governments have apps, celebrities have multi-million
dollar websites, and the Department of Defense (DOD) have combat systems that
rely on open source programs to important strategic mission requirements. The
fact is that all of these organizations are progressively becoming more
dependent on open source programs to be effective. Consequently, having no
safeguards to protect them from the introduction of a vulnerability can have
significant implications to their budget, readiness, and
capabilities<sup>1</sup>.

The idea of embedding compromised open source programs into DOD's operational
combat systems is troubling for obvious reasons. Failure in these systems can be
costly in terms of money, time, and human life. This project aims at endowing
computers with the ability to infiltrate a type of behavior that is indicative
of adversaries rather than of the situation. Computers will be able to
reconstruct, in an online fashion, a sequence of code states that took place
before, during and after the committing code changes and determine whether those
changes exhibit symptoms that may be indicative of harmful bugs and/or security
flaws.

We narrow the scope of this project by studying open source programs embedded in
hardware systems, specifically software utilized by small Unmanned Aerial
Vehicles (UAVs). At DARPA's Mining and Understanding Software Enclaves (MUSE)
program, we focused on leveraging a snapshot of the hundreds of billions of
lines of open source code available today to develop _new_ approaches for
automatically constructing, transplanting, and repairing programs in UAVs. Now,
we will leverage the evolution history of software written by accomplished
developers to produce pluggable analyzers that can infiltrate this type of
adversarial behavior<sup>2</sup>, and then determine the suitability of
individual open source programs for UAVs missions.

#### DARPA Pitch

#### Three Heilmeier Questions

1 _What are you trying to do? Articulate your objectives using no jargon_.   

We are going to develop a set of probabilistic models and capabilities for
automatically identifying malicious source code inserted to open source programs
before their embedding into UAVs systems. Our approach is a fully data-driven
approach and thus requires to learn to capture, from data<sup>3</sup>, certain
coding habits either specific to star programmers (and their teams) or specific
to their code bases. These habits are sensitive to the presence of malicious
code in codebases, and can be represented in a form that we can algorithmically
operationalize.

2 _How is it done today, and what are the limits of current practice?_

While each new generation of approaches and tools help tackle the problem of
extracting code patterns (buggy code, redundant code, etc) from a large body of
open source code using software repository mining techniques, the solutions
focus on the discovery of known patterns and they target applications such as
refactoring of duplicate code. In contrast, this project focuses on discovering
new patterns from the ground up.

3 _What is new in your approach and why do you think it will be successful?_

Besides learning to capture a type of wisdom that is intrinsic to humans, we are
building on experimentally validated data mining techniques for introspecting
software repositories, and extending them by bringing in aspects of program analysis
and verification, machine learning, and cognitive science.

#### Footnotes

<sup>1</sup>In the case of the DOD, it can have an significant impact on the
capabilities of their armed services.

<sup>2</sup>Introduction of new and unforeseen pieces of code, which are
unlikely to occur in that codebase and exhibit symptoms that may be indicative
of harmful bugs and/or security flaws.

<sup>3</sup>Software evolution history of open source projects professional
developers have written throughout numerous years.
