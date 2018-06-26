<img src="https://github.com/hsanchez/greenlinters/raw/master/greenlinters.png" width="250">

## Green Linters

We will mine emergent programming mis-behavior from the source code  and social
activities in GitHub open source projects (OSPs) to codify destructive  programming
behavior that lead to the embedding of potential vulnerabilities into critical
systems. By modeling emergent programming mis-behavior, we can enable algorithms
for finding OSPs that have been repackaged with vulnerabilities before their
embedding into critical systems.

### Adversarial Generative Models of Software Development

We will mine the events and social interactions in open-source projects (OSP) on
GitHub to predict emergent programming mis-behavior (social, coding habits, and
the combination of both). We will determine the ground truth by a chain of
social activities, code changes, and pull requests that lead to a failure of a
test-case or a series of test cases during the integration of those changes into
the main product code (i.e., during continuous integration). Current approaches
focus almost entirely on the code itself, while ignoring the rich social
interactions and user-specific parameters we can  use as features in predicting
misbehavior. We will develop a new method of predicting emergent misbehaviors
based on user parameters and interactions that are generalizable across
languages and project types. Additionally, we will use these misbehavior models
to create adversarial generative models of misbehavior that one can use as
attack vectors to explore the vulnerability of open-source projects.  These
attack vectors range from catastrophically distracting pull requests
("pull-request DDoS") to manipulation through sock puppets.  This work is
critical because critical systems embed numerous OSPs as dependencies so it is
imperative to catch these problems before they become serious security risks.   


### Contributions

We have a [set of guidelines](CONTRIBUTING.md) for contributing to Green
Linters.  These are guidelines, not rules. Use your best judgment, and feel free
to propose  changes to this document in a pull request.


### Archive

Details of the _Unlikely code_ idea can be found [here](Unlikely.md)
