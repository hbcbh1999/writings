## The Meaning of Semantic Versioning

Does semantic versioning mean anything? The answer is not much.

When I go look at a library semantic versioning will tell me that the library has
three numbers associated with it. They are called the major, minor and patch but really
the only information they convey is that if the major number changes at some future date
I better watch out because all my code could break! That's so hetero.

The minor and patch numbers tell me absolutely nothing except that something changed which I as a user
absolutely do not give a crap about because my code will keep working.

That my friends is the gist of semantic versioning.

## Current state of affairs

Let's think about what I care about as a developer when using someone else's software.

1. How do I use it?
2. When things change in the future:
  1. Will my code work?
  2. What changed?
3. How bug ridden is the software?
  - aka how well does it fulfill its promises without ugly surprises.
4. How active is development on the software?

For #1 we have the following
1. Documentation
2. Examples

For #2 we have
1. semantic versioning
2. renaming our package to something else i.e. from foo to foo2

For #3 we have
  1. github issues
  2. bug trackers
  3. number of downloads

For #4 we have
  1. git commits


## Can we do better?

So now the question is how much of this information could we potentially
pack into a versioning scheme?

We could start by using timestamps and removing the minor versioning number, because
as much as we might like him he is totally pointless from an informational content perspective.

So a version of `artifact.last-change` i.e. `1:2017.05.22` would tell me that I'm using the version 1 of
some library and the last time someone changed the code base was May 22, 2017.

I use this lib and a couple of days later I see `1:2017.06.03`. I'm happy and upgrade because I know my code will just keep working.

Whenever they finally release breaking changes the new version will look something like `2:2021.03.10`. Now I can decide whenever I want too
to upgrade to version 2. And patches for the old version can still be made and I can upgrade without fear to `1:2021.03.15`.

This gives us a little more information than semver and seems a lot simpler to me.

But we could make this very descriptive if we wanted. It would just be hard to generate a simple number.

```json
{
  "artifact" : "2017.03.25",
  "last-release" : "2017.04.11",
  "code_examples" : true,
  "bug_count" : 22,
  "last_bug_fix" : "2016.03.24",
  "commits_last_180_days" : 1,
  "commits_last_year" : 4,
  "age_months" : 38
}
```

How much can we scrunch this number up?
We can represent a year as 365 days, and so the percentage of the year would be n/365. that gives us 2 digits after the year.

Thus 2017.03.25 becomes 2017.23 and 2017.04.11 becomes 2017.28.

The only other thing I would possibly care about is new functionality that doesn't break old changes. We'll let that be a bit.

So our new semver looks like: `1:2017.28:0` for an initial release.
Afterwards comes `1:2017.44:1` in which some new features were added - I might want to check them out.
Then comes just a bugfix release `1:2017.51:0`.
Years later comes the long awaited version 2 as `2:2019.00:0`.

#### Wrapping Up : Ideas easily conveyable with number(s)

1. Anything binary:
  - added features? [y/n]
  - new deprecations? [y/n]
  - breaking changes? [y/n]
  - added examples/docs? [y/n]
  - bug fixes? [y/n]

```
<added-features> : <added-deprecations> : <added examples/docs> : <bug-fixes>.
```

that means I can display this information using just 4 bits which is cool because
now I can use 1 hex digit to represent the information.

the format:
```ruby
# A added features release number
version = 8

# A added deprecations release
version = 4

# a added examples/docs release
version = 2

# a bugfix release
version = 1

# A release with added features and added deprecations
version = C

# a release with added docs and some bugfixes
version = 0x03

# a release with features, deprecations, and bugfixes
version = D

```

So now we could combine everything:

A version is 1 release with some added features and bugfixes is

```ruby
  version =  "1:9:1491609731992"
```
This the unix timestamp for when the release occurred, exactly what the release
contained (features + bugfixes) and that my code will keep working because its
still version 1.
