# Minutes for the Node.js core team meeting of 2015-04-17

## Participants

* [Alexis Campailla](https://github.com/orangemocha)
* [Colin Ihrig](https://github.com/cjihrig)
* [Julien Gilli](https://github.com/misterdjules)
* [Michael Dawson](https://github.com/mhdawson)
* [TJ Fontaine](https://github.com/tjfontaine)
* [Steven R. Loomis](https://github.com/srl295) (scribe)

## Discussions

### Releases

#### v0.12.3

JGI: some progress , still slow.
On v8 upgrade [#9185](https://github.com/joyent/node/pull/9185), made
progress, trevor is working on until next week.
Additional patches all in the comments.
Help wanted to finish v8 integration.

##### Profiler

JGI: [#14576](https://github.com/joyent/node/issues/14576) An issue -
profiler causing v8 to stall?

##### FreeBSD flag

JGI: [#8540](https://github.com/joyent/node/issues/8540) - FreeBSD
flag. Input needed. The parameter is exposed to JS.

JGI: finishing other P-1 issues before release.

### Other discussions

#### Bar Mitzvah

JGI: [#15445](https://github.com/joyent/node/issues/15445) - Bar
Mitzvah issue - 2 questions, feedback needed:

* Need to be able to get prior (insecure) behavior back if needed.
* How best to name the option?

MD: Don't want to do this in perpetuity - RC4. Expand documentation.

SRL: Should it be named 'enable-insecure'?

JGI: Always possible for users to specify custom cipher lists.

TJ: Balance between platform users and application users.

JGI: Need to get the main scenarios, come up with use cases first.

MD: This is a tempoary fix, most people (hopefully) are using defaults.

TJ: This setting is used more in minor versions, when people are
bringing up [some version of an] app.

#### Wrong checksum for node v0.12.2

JGI: This issue will be investigated.

#### Leap Second

SRL: Existing issue: [#9382](https://github.com/joyent/node/issues/9382)

SRL: Probably can do more testing.

TJ / JGI: - did a test suitewith faketime. That may not work on windows.

TJ: "no known issues" - some may want more documentation.

TJ: Blog post, link to documentation/faq.

TJ/AC: Clock used on windows for 0.10 is less precise but still monotonic.

MD: Google response on v8 - "thats a good question".

TJ: This should be first class documentation.

Action: SRL to open a new ticket. Document that Date.now != how timers work.
(in `doc/timers`).

#### Documentation of OpenSSL upgrades

JGI: Need to document openssl upgrades:
* Upgrades can be confusing
* Often these upgrades are done in 'less than ideal' situations
(pressure to fix a critical issue).

#### Documenting how to upgrade v8

James and Julien are working on docs of how to do the update,.
Missing some of the history, but at least it can be well understood.
Ideally anyone on the team or community can understand how it is done.

TJ: no specific home for this doc, in the wiki right now (link)

JGI: Current state of the documentation may not include all floating patches.

TJ: docs should live in the code eventually.
JGI: may take another form.

Action: SRL: document how to upgrade ICU.

#### Joint node.js/io.js meetings

CI: joint TC call.

ALL: People don't want extra meetings - may be a little disorganized.

TJ: - hard but necessary -- there's a lot of work to do around merging
two projects:

* Need to work together to maintain stable release (LTS/platform etc)
has to be comfortable integrating into the entire project.
* Innovation + ideals of LTS working group.  Required amount of tension.
* Hopefully good agendas.

SRL: More of a concatenation than a merge. agenda and time management
will become critical.

TJ: Needs time management - "we have 5 minutes to discuss this".

ALL: Proposed time is "Wednesday and it has been 1pm-2pm pacific since PDT
kicked in (it was noon-1 before that)."

ALL: This time seemed good.

SRL: Formal scheduling of agenda items?

TJ: Yes, people should propose a time length when items come in.

JGI: Two goals - 1. identify divergence, and 2. get used to other members.

JGI: Maybe 15 minutes joint meeting, then individual meetings if needed.

#### Call for help triaging incoming bugs

JGI: Help wanted triaging incoming bugs.

#### Crash from command line (Intl)

SRL: investigating crash from command line
[#9361](https://github.com/joyent/node/issues/9361).
