# About Zen Versioning Spec ("ZenVer")

Zen Versioning, "Zen Ver" or "ZenVer" is an alternative versioning spec that
aims to be simple, elegant or "zen".

## Introduction

> In the world of software management there exists a dreaded place called
> "dependency hell." The bigger your system grows and the more packages you
> integrate into your software, the more likely you are to find yourself, one
> day, in this pit of despair.

> In systems with many dependencies, releasing new package versions can quickly
> become a nightmare. If the dependency specifications are too tight, you are in
> danger of version lock (the inability to upgrade a package without having to
> release new versions of every dependent package). If dependencies are
> specified too loosely, you will inevitably be bitten by version promiscuity
> (assuming compatibility with more future versions than is reasonable).
> Dependency hell is where you are when version lock and/or version promiscuity
> prevent you from easily and safely moving your project forward.

> As a solution to this problem, we propose a simple set of rules and
> requirements that dictate how version numbers are assigned and incremented.
> These rules are based on but not necessarily limited to pre-existing
> widespread common practices in use in both closed and open-source software.
> For this system to work, you first need to declare a public API. This may
> consist of documentation or be enforced by the code itself. Regardless, it is
> important that this API be clear and precise. Once you identify your public
> API, you communicate changes to it with specific increments to your version
> number. Consider a version format of X.Y.Z (Major.Minor.Patch). Bug fixes not
> affecting the API increment the patch version, backward compatible API
> additions/changes increment the minor version, and backward incompatible API
> changes increment the major version.

> We call this system "Semantic Versioning." Under this scheme, version numbers
> and the way they change convey meaning about the underlying code and what has
> been modified from one version to the next.

― From [https://semver.org](https://semver.org/#introduction)

On paper, this all seems great. Except for one problem: all of that is
**bullshit**. The clear solution, as most of my peers who have formerly worked
on designing a good versioning specification fail to realise[^1], is to avoid
complications while versioning our software, and obviously, to increment
`VERSION` every time you make a change to remain as straightforward as possible.
To remain Zen.

> API documentation this, minor revision that. BULLSHIT[^2].

We will see that the underlying problem in existing versioning specifications is
that there is no good, consistent specification that is not demanding of the
developer. Consistency comes from simplicity, and we cannot achieve neither
simplicity nor consistency with those overcomplicated specifications that
require more from the developer.

> `0.40.3`? `1.5.0`? You hit your head pretty hard, get up we are going back to
> _proper_ versioning.

To all problems previously (poorly) addressed by SemVer and ZeroVer, ZenVer
proposes a simple set of rules that are based on _necessarily_ pre-existing
widespread common practices in use in both closed and open-source software[^3].

For this system to work, you must know _how numbers work_[^4]. That is about
all, you need not to document anything, nor to enforce it by the code itself.

Once you identify your own software (i.e. software that you are working on),
which should not be _too_ difficult, you may consider a version format of `X`
(VERSION). Bug fixes increment the VERSION by one, backward compatible API
additions/changes increment the VERSION by one, and backward incompatible
incompatible API changes increment the VERSION by one. In fact, anything
increments the VERSION by one. A butterfly flapping wings on the other side of
the earth may increment VERSION by one if you are not careful.

> While incrementing by one is the common practice in Zenver, we acknowledge the
> needs of a developer and propose that if you are, in any given time, feeling a
> bit down, then you may consider bumping VERSION arbitrarily to feel better.

In former iterations of this specification, some users that _major_[^5] changes
do not impose the sense of importance that they need to. To that, ZenVer's
answer is incrementing: not by one, but by two (or perhaps more) depending on
how major the change really is.

> Our motivation? Two is larger than one.

### Motivation

The field of software development has long been littered with overcomplicated
versioning specifications that seem to be invented solely to waste the
developers' time by inventing made-up requirements that, in truth, nobody has
the time to follow. Developers are busy people.

> _Some of them are too busy to read this document! By all means, stop reading
> here if you have gotten the gist of ZenVer already!_

We should consider not only that it takes time to calculate version numbers, but
also that it takes mental strain: counting is hard. We do not want to spend time
and effort that could be spent developing software on devising versions for our
software.

> You will never need to ask yourself "do I need to bump minor or major?" You
> will simply write software.

ZenVer was created to address the poor design choices of prior, unaffiliated
specifications by proposing (but not enforcing) a simple, _zen_, specification
that works anywhere, for anyone. It also removes the need to conjure up new,
even dumber specifications a total of 7 people will use.

> In other words, one spec to rule them all!

## FAQ

### What does `z` in versions stand for?

It's short for _"zersion"_.

### Can I contribute?

Sure, see [CONTRIBUTING](CONTRIBUTING.md).

### Why make a new spec?

It's funny.

### Is this serious? Can I use it?

No, and yes. ZenVer is a joke, plain and simple. But you are welcome to use it
for any project that you might want to version in a straightforward manner.

[^1]:
    If this has not yet been made obvious to you, then I feel responsible for
    informing you that **this is a joke**. I harbor no ill will towards SemVer
    or any other versioning specification. Though, I prefer ZeroVer over SemVer
    because it has a more interesting premise. You will find obvious references
    to the ideas behind both specifications.

[^2]:
    [An obvious Max0r reference](https://www.youtube.com/watch?v=VkLYPCJogzM)
    because I find his writing pretty darn funny

[^3]:
    We should probably learn about versioning from Microsoft. Confused? Take a
    look at Windows' versioning scheme. At the time of writing, the latest
    supported revision is `22631.3527`. What the hell does that even mean?

[^4]:
    If you have having trouble with this, then there is not much ZenVer can do
    for you. May I suggest revising on your elementary school mathematics?

[^5]:
    You should ask yourself: how major is my major change? If it's more major
    than major, then increase the number in accordance. If it's less major than
    major, then repeat above instructions. I think I'm repeating myself here.
