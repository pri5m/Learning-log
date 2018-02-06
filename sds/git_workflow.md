
# Git workflow

# Git-flow

- Two permanent branches

- Three types of temporary branches

**Goals**

- A known set of working practices shared by a team

- A known 'good' version ready for production

- A safe place to develop

- A safe place to intergrate

- A safe place to fix live issues

- A safe place for final quality assurance (QA)

- A known set of events to start automation

**The main branches**

There are two eternal branches

- Master

- Develop

The head of the master branch on origin is deemed to be always production-ready

The head of the develop branch on origin is deemed to be the lastest ready features for the next release

Based on well-understood events

Whne develop branch is stable, Merge develop into master. Tag master with a release number

Any merge to master creates a produciton release

*Supporting branches*

- Feature branches

- Release branches

- Hotfix branches

These are created on demand and deleted after use(not for assessment tho)

NOT SPECIAL IN GIT TERMS, THEY ARE JUST BRANCHES

**Feature branch**

May branch off from: develop

Must merge back into: develop

Naming convention:

May (some say typically) only exist in developer repo: Last couple day max

Create branch from develop

*git checkout -b myfeature develop

Merge branch into develop

*git checkout develop

git merge --no-ff myfeature   //no fastforwarding, forces git to create a new git commitment, 'ha' topic


**Release branches**

May branch off from: develop

Must merge back into: Develp and master

Branch naming convention: release-*

*Rules*

- Work that can be done on a relase branch


**Hotfix branches**

May branch of from: master

Must merge back into: develop and master

Branch naming convention: hot-fix*

**Pros and cons**

Overkill- no need fro two eternal branches. Everything can be done on master

Impact on choice

- Team size

- Timezones

- Size and scale of project

- Dev ops (speed- its fast, slowly becoming the norm)

- Culture (risk adverse- no risks)

- Development techniques

- Type of deployment

- Frequency of deployment

# GitHub flow

No develop branch, only master

```
For teams that have to do formal releases on a
longer term interval (a few weeks to a few
months between releases), and be able to do
hot-fixes and maintenance branches and other
things that arise from shipping so
infrequently, git-flow makes sense and I would
highly advocate it’s use.
```
