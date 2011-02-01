---
title: Weekend Update, January Edition
author: Bob McWhirter
layout: news
---

[benblog]: http://thinkingconcurrently.com/
[markblog]: http://markclittle.blogspot.com/
[cr1jira]: https://issues.jboss.org/secure/IssueNavigator.jspa?reset=true&jqlQuery=fixVersion+%3D+%221.0.0.CR1%22+AND+project+%3D+TORQUE+ORDER+BY+resolution+DESC%2C+key+DESC

I really enjoy the weekly recaps that [Ben Browning][benblog] has been producing for
[SteamCannon](http://steamcannon.org/).  I also have a [boss][markblog] who likes
end-of-the-month updates.  Considering TorqueBox is open-source, I might as well 
kill (or just injure) two birds with one stone.  

Hi, Mark.  *Here's your status report*.

I'd like to try posting these every weekend, but we'll see how it goes.  For now,
this one will wrap up all of January, because a lot has been afoot lately.

## Team

First, I'd like to happily welcome the increased participation within the TorqueBox
project by Lance Ball, Ben Browning and Toby Crawley. We're of course already familiar
with them from the [SteamCannon](http://steamcannon.org/) project. Expect great things
from these guys.

## A note about versioning...

At [JBoss](http://jboss.org/), the version-numbering scheme includes the suffixes
of `Alpha`, `Beta`, `CR`, and either `Final` or `GA`.  The `CR` suffix is used to
denote a *candidate release*, which the rest of the world calls a *release candidate*.

Given that the next release will be a candidate release, it must potentially be
able to be declared "done" and released as the final.  This means the CR1 release
will wait until we have [no outstanding JIRAs][cr1jira].  CR is not just a fancy name for
"beta".

## Action Items

A variety of improvements have occurred this month.  They will all be included
in the upcoming `1.0.0.CR1` release.

Jim Crossley attacked several issues, including [session replication](https://issues.jboss.org/browse/TORQUE-199),
[message processor concurrency](https://issues.jboss.org/browse/TORQUE-195), and [messaging reliability](https://issues.jboss.org/browse/TORQUE-207),
along with a variety of VFS fixes. 

Additionally, Jim produced a [fantastic 3-part series on cluster-related issues](/news/2011/01/04/clustering-torquebox/).

Ben Browning worked in support for [synchronous queues](https://issues.jboss.org/browse/TORQUE-235), and wrote an [awesome article 
about long-lived services](news/2011/01/28/services/).  

Toby Crawley added support for any object to have [asynchronous tasks](https://issues.jboss.org/browse/TORQUE-213).  
Very easily TorqueBox now supports the same sort of idioms as `delayed_job`.

Lance Ball is leveraging his [BoxGrinder](http://boxgrinder.org/) knowledge to produce [easy-to-consume AMIs](https://issues.jboss.org/browse/TORQUE-228),
is working on better [RVM support](https://issues.jboss.org/browse/TORQUE-222), all
in support of his goal of Heroku-esque [`git push` easy deployment](https://issues.jboss.org/browse/TORQUE-221).

I (Bob) worked on Windows compatibility, improved and documented [Capistrano support](/news/2011/01/20/capistrano-and-torquebox/), 
and started slimming the binary distribution (45% smaller!) by restricting the gems and profiles we include.

We tried the JRuby 1.6.0.RC1 release, and while it seemed to function within TorqueBox itself, it exhibited regressions
when used with our [integration test harness](/news/2010/12/20/rspec-with-arquillian/).  We eagerly await the 1.6.0.RC2 release from the JRuby team.

## Planning

This past week, the team held a *post-1.0* [planning meeting](/news/2011/01/24/planning-meeting-recap/) on IRC.
A lot of great ideas were generated by the community, along with some fantastic use-cases.  We're all quite
excited as to where TorqueBox will go after the 1.0 release.

## Upcoming Talks

This upcoming weekend, Jim Crossley will be presenting *Crank Up Your Apps With TorqueBox* at the 
[MagicRuby](http://magic-ruby.com/) conference in Orlando.  Ben and Toby will also be present, with
stickers that would look awesome on your laptop.  Drop by, strike up a conversation.  Earn yourself a knob (or a monkey).

![Stickers](/images/misc/stickers.jpg)

## Site Update

In preparation for the hordes of visitors after Jim's talk, we're sprucing up the site.  Upcoming
talks are displayed on the front page, and more latest news is shown.  Plus, more knob.

## Links

* Sessions
  * [TORQUE-199](https://issues.jboss.org/browse/TORQUE-199): Session replication
* Messaging
  * [TORQUE-195](https://issues.jboss.org/browse/TORQUE-195): Queue concurrency
  * [TORQUE-207](https://issues.jboss.org/browse/TORQUE-207): Messaging reliability
  * [TORQUE-235](https://issues.jboss.org/browse/TORQUE-235): Synchronous queues
  * [TORQUE-213](https://issues.jboss.org/browse/TORQUE-213): Mimic delayed_job's handle_async
* Deployment & Systems
  * [TORQUE-221](https://issues.jboss.org/browse/TORQUE-221): Heroku-esque git push deploy
  * [TORQUE-222](https://issues.jboss.org/browse/TORQUE-222): RVM support
  * [TORQUE-228](https://issues.jboss.org/browse/TORQUE-228): Friendly AMIs
* Articles
  * [Long-running Services](/news/2011/01/28/services/)
  * [Capistrano](/news/2011/01/20/capistrano-and-torquebox/)
  * [Clustering](/news/2011/01/04/clustering-torquebox/)
  * [Session Replication](/news/2011/01/06/session-replication/)
  * [Background Tasks](/news/2011/01/07/clustered-tasks/)