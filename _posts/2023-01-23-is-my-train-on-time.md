---
id: 4
title: 'Is my train on time?'
date: '2023-01-23T09:13:46+00:00'
author: dan
layout: post
guid: 'https://visualengineer.org/?p=4'
permalink: /2023/01/23/is-my-train-on-time/
image: /assets/2023/01/departure-board-feature.png
---

Deutche Bahn has a app (DB Navigator) which has real-time info on train services in Germany. One of the pages is called “Is my train on time?”. Whenever I open the page, I expect to see this:

<figure>
<img src="/assets/2023/01/db-navigator.png">
<figcaption>
You should be thankful it hasn’t been cancelled.
</figcaption>
</figure>

Internationally, Germany has a reputation for punctuality. The reality is different. Many years ago my wife was explaining to a German friend that she had missed a connection between two DB trains. The conversation went like this:

> – “How much time did you allow for the connection?  
> – “15 minutes.”  
> – “Haha, you should always allow one hour. If you want punctual trains you should go to Switzerland!”

In fairness, Deutche Bahn has a difficult job. They have neighbours on all sides, with hundreds of cross-border train journeys each day. Delays from abroad are frequent, and have knock-on effects to the rest of the German rail network.

DB describes a stop as punctual “if the scheduled arrival time was exceeded by less than six minutes”. That doesn’t leave a lot of room to play with. Regional trains often run on time (93% in 2022[^1]), but the performance of long-distance trains is much worse (70% in 2022[^1]).

I was interested in the on-time running performance of DB’s long-distance InterCity Express (ICE) trains. The ICE is DB’s flagship service, with the fastest and most comfortable trains (and the most expensive tickets). My children call ICEs “fast white trains”.

<figure>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/ICE_3_Oberhaider-Wald-Tunnel.jpg/1024px-ICE_3_Oberhaider-Wald-Tunnel.jpg">
<figcaption>
This is a stationary ICE3, stuck somewhere between Cologne and Frankfurt (source: <a href="https://commons.wikimedia.org/wiki/File:ICE_3_Oberhaider-Wald-Tunnel.jpg">Sebastian Terfloth</a>)
</figcaption>
</figure>

I looked at the ICE punctuality stats for the months of June, July, and August 2022, using data from the fantastic website [Zugfinder](https://www.zugfinder.net/en/start)[^2]. I wanted to analyse the whole of 2022, but getting hold of the arrival and departure times for the whole year was just too onerous. Summer 2022 interested me because it was a particularly difficult time for Deutche Bahn. Passenger numbers on local trains were much higher than usual, because of a temporary travel subsidy that allowed unlimited travel in Germany for €9/month. The local trains were extremely crowded[^3], and this had flow-on effects for the long-distance trains too.

Here is a summary of the analysis of ICE services from Summer 2022:

{: .auto}
| Description      | Count   |       |
|------------------|---------|-------|
| Number of days   | 92      |       |
| Trains scheduled | 45,982  |       |
| Trains cancelled | 1,612   | (4%)  |
| Punctual stops   | 271,327 | (51%) |
| Late stops       | 225,807 | (42%) |
| Cancelled stops  | 31,822  | (6%)  |

The average delay was 11 minutes, but some delays were much worse. If we took a histogram of delays in a perfectly punctual rail system, there would be a large peak at 0-1 minutes, and no tail at all. Here is what the actual histogram of delays looks like for our dataset (with Japan[^4] as a comparison).

<figure>
<img src="/assets/2023/01/average-delay.png" class="w-600">
<figcaption>
Japan doesn’t have to share trains with its neighbours though...
</figcaption>
</figure>


Some stations fared worse than others. The stations with more punctual trains tend to be at the end of the line (e.g. Hamburg in the north, and Munich in the south).

<figure>
<img src="/assets/2023/01/average-delay-stations.png" class="w-600">
<figcaption>
The winner of most punctual station is Interlaken Ost (in Switzerland).
</figcaption>
</figure>

If your train is delayed by more than one hour things start to get interesting. Under the Passenger Rights Regulation (“Fahrgastrechte”), DB will refund part of your ticket price (25% for delays &gt; 60 minutes, 50% for delays &gt; 120 minutes). You submit your Passenger Rights Claim form by post, because Germany loves posting physical mail (OK, you can use an app[^5], but only since 2021). There are a few companies that actually complete the paperwork for you (for a fee) because there are so many late passengers chasing compensation[^6]. One website has a list of delayed trains from the past week, with pre-filled PDFs ready for you to download[^7].

<figure>
<img src="/assets/2023/01/bahn-pender.png" class="w-600">
<figcaption>
Your pre-filled compensation form is just one click away.
</figcaption>
</figure>

I looked at the routes which were least likely to have delays, and there were a few patterns which led me to create some travel guidance.

__Recommendations for punctual ICE train journeys:__

- Keep your journey short (\<250 km);
- Don’t pass through Frankfurt in the middle of your journey; and
- For the love of all things holy, avoid West Germany.

If you follow these rules your train is likely to run on time, and you can enjoy your visit to exotic destinations like Dresden or Rostock:

<iframe height="700px" link="false" loading="lazy" logo="false" modebar="false" src="/assets/2023/01/good-trains.html" width="100%"></iframe>

If you don’t heed the advice above, your journey is likely to make additional stops in the following stations:

- Pain;
- Torment;
- Malaise; and
- Mannheim Hbf.

<iframe height="700px" link="false" loading="lazy" logo="false" modebar="false" src="/assets/2023/01/bad-trains.html" width="100%"></iframe>

Why are all the trains delayed? At face value, Deutsch Bahn appears to be pretty transparent about this. The departure boards at major train stations will list all current trains and a description of any delays. It’s still frustrating when it is your train that happens to be late, but DB has decided that their customers would like to know *why* their train is late, rather than just by how long. Here is an example of the departure board at Frankfurt Main Station, as I write:

<figure>
<img src="/assets/2023/01/departure-board.png" class="w-600">
<figcaption>
I hope nobody had a seat reservation on the missing coach.
</figcaption>
</figure>

The reasons are varied and numerous, but after a while they all become familiar. Some cynical travellers might question the stated reasons for the delay, imagining a bored DB employee sitting at a control panel deciding which button to press next.

<figure>
<img src="/assets/2023/01/blame-allocator.png" class="w-600">
<figcaption>
If in doubt, blame the neighbours.
</figcaption>
</figure>

Some of the reasons for train delays are banal, e.g. “Delay of a previous train”; others are more dramatic, like the one from this tweet:


<blockquote class="twitter-tweet"><p lang="en" dir="ltr">German punctuality is a bit of a myth. Slack station work, a broken down freight train, signal failure, a train in reverse formation, and an unexploded WWII bomb (ok that wasn&#39;t their fault) made for a fraught journey of frantic dashes, unexpected stops, and missed connections. <a href="https://t.co/H3kZICglkx">pic.twitter.com/H3kZICglkx</a></p>&mdash; Philip Dyer-Perry (@PGPDP) <a href="https://twitter.com/PGPDP/status/1169160321975619590?ref_src=twsrc%5Etfw">September 4, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 


 <script async="" charset="utf-8" src="https://platform.twitter.com/widgets.js"></script>I collected all the primary reasons for delays on Deutsche Bahn ICE services in 2022 from [zugfinder](https://www.zugfinder.net/en/start)[.net](htts://www.zugfinder.net). Here is the abridged list:

{: .auto}
| Reason for ICE delays in 2022                | Count  |
|----------------------------------------------|--------|
| Delay of a previous train                    | 33,868 |
| Repair on the train                          | 15,438 |
| Construction work                            | 8,110  |
| Waiting for connecting travellers            | 7,945  |
| Staff late from previous trip                | 6,039  |
| Train late from previous trip                | 5,190  |
| Repairs to track                             | 4,338  |
| Repairs to signal                            | 3,698  |
| Repairs to points                            | 3,003  |
| Police operation                             | 2,483  |
| Unauthorized people on the route             | 2,359  |
| Signal defect                                | 1,601  |
| Storm                                        | 1,581  |
| Emergency doctor on the route                | 1,437  |
| Delay from abroad                            | 1,375  |
| Repair on the overhead line                  | 1,176  |
| Detour                                       | 750    |
| Defective door                               | 587    |
| Medical care of a passenger                  | 572    |
| Fire brigade operations on the route         | 509    |
| Objects on the route                         | 364    |
| Passport control and customs                 | 245    |
| Animals on the track                         | 217    |
| High passenger numbers extend entry and exit | 179    |
| Defusal of bomb\*                            | 174    |
| Weather-related impairments                  | 144    |
| Staff sickness                               | 130    |
| Impairment by vandalism                      | 122    |
| Fallen tree on the route                     | 109    |
| Strikes                                      | 80     |
| Damage to a bridge                           | 76     |
| Unauthorized use of emergency brake          | 38     |
| Accident at level crossing                   | 33     |
| Landslide                                    | 30     |
| Snow and ice                                 | 23     |
| Due to the weather, reduced speed            | 18     |
| Waiting for a late ship                      | 3      |
| Technical disorder on a different train      | 3      |
| Flood                                        | 1      |
| **Bomb defusal was required on 31 separate days*      |


The overwhelming majority of delays are primarily caused by “train repairs”. Train repairs are usually minor issues, according to railway enthusiasts [^8] and are more likely to be “a passenger jammed the door with their suitcase”, rather than “the wheels fell off”. Apparently DB used to say “train defect”, but they decided that “train repairs” sounded better.

What should you do if your train is delayed? Hopefully you are already on board, in which case you can make your way to the restaurant car and pick up a handful of complimentary DB cookies and chocolates.

<figure>
<img src="https://cdn.onemileatatime.com/wp-content/uploads/2020/10/Deutsche-Bahn-ICE-First-Class-34.jpg" class="w-500">
<figcaption>
The cookies are really quite tasty (source: <a href="https://onemileatatime.com/deutsche-bahn-ice-first-class-review/">Ben Schlappig</a>)
</figcaption>
</figure>

There’s free Wi-Fi too, so you can install some software updates while you’re waiting for your train to start moving. You can also plan how to spend your partial ticket refund, and start filling out your Passenger Rights Claim form. DB is actually very punctual when it comes to processing these!

#### References

[^1]: [DB – Integrated Interim Report 2022](https://zbir.deutschebahn.com/2022/en/interim-group-management-report-unaudited/product-quality-and-digitalization/punctuality/)
[^2]: [zugfinder.net](https://www.zugfinder.net/)
[^3]: [DW – Did Germany’s 9-euro train and bus ticket pay off?](https://www.dw.com/en/9-euro-ticket-germany-winds-down-experiment-with-low-cost-train-travel/a-62962871)
[^4]: [JR – About Shinkansen](https://global.jr-central.co.jp/en/company/about_shinkansen/)
[^5]: [DB – Passenger Rights Claim Form](https://www.bahn.com/en/booking-information/passenger-rights/passengers-rights-claim-form)
[^6]: [The Local – How German start-ups are profiting from Deutsche Bahn delays](https://www.thelocal.de/20200106/how-german-start-ups-are-profiting-from-deutsche-bahn-delays)
[^7]: [http://bahn-pendler.de/](http://bahn-pendler.de/)
[^8]: [ICE Treff – Reparatur am Zug](https://www.ice-treff.de/index.php?mode=thread&id=65975)

