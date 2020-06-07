---
title: "Golf analytics"
authors: ["admin"]
tags: ["golf", "data analysis"]
categories: ["golf"]
date: 2020-05-30T23:45:44-04:00
#lastmod: 2020-05-30T23:45:44-04:00
#featured: true
#draft: false
commentable: false
image:
  placement: 1
  caption: ""
  focal_point: "Center"
  preview_only: false
---

If you didn't know already, I have a (pretty healthy) obsession with the game of golf. When I was younger it translated into spending whole days at the golf course over summer, and now it mostly means I listen to an unhealthy amount of golf podcasts where any normal person wouldn't get 99% of the references to professional golf. Additionally, I've become very interested in the data analytics in golf that have vastly been improved by advanced data collection over the last 15 years.

Before the year 2004, the data collected in professional golf was usually very simple. How long was your drive, did it hit the fairway, did you hit the green in the right number of shots, how many putts did you have on this hole. This was usually collected for every hole, although depending on the resources, distance measurements were limited to fewer holes due to the requirement of measuring tools. While this data said *something* about how that player performed, it did not tell *everything* and a lot of times it was even easy to make the wrong conclusion. 

As an example, imagine a player missed the green slightly, leading to them needing to make a chip. They do the shot and it leaves a very short put to tap in, lets say 2 feet. The player makes the put, and goes away with a par. With traditional stats, this could be described as:

- Fairway: 1/1
- Green: 0/1
- Putts: 1

Looking at this data without knowledge about what actually happened during the hole, one *could* make the conclusion that the player made a good putt to save par, while in reality it was the chip that was good and the putt was just a foregone conclusion. Additionally, was the reason for the missed green a difficult (read long) approach shot, or was it more of a bad shot? A lot of assumptions have to be made with this limited information, so what information would we like to have here? Ideally, we would like to know

- The underlying conditions for each shot
- The underlying conditions from the spot where each shot ended up

Ideally, all parts of the condition of a shot could be quantitized, but this is not possible. 

- How much would having a tree to shoot over increase the difficulty? 
- How much would having to carry the shot over a bunker increase the difficulty?
- How much would a hard green compared to a soft green increase the difficulty?

With enough data (read, A LOT) it might be possible to quantify all of these conditions, but since a lot of them also interact with each other, it is simply not possible. Instead, we have to normalize and simplify the conditions into a few simple factors. Enter **Mark Broadie**. In 2014, he published his book [*Every Shot Counts*](https://www.amazon.com/Every-Shot-Counts-Revolutionary-Performance/dp/1592407501), which one could say, was the Moneyball moment for golf. He introduced a system to quantitavely determine the condition of a shot, and based on the condition of where the shot ended up,he could also determine how *good* the shot was. How did he do this? He introduced two variables that determined the condition of a shot:

- Distance to the hole
- Lie (e.g. fairway, rough, green, sand)
  - It should be noted here that he also introduced a more arbitrary *recovery* lie, which simply covered shots where the player couldn't directly aim for the whole but simply had to recover from the position they had put themselves in. 

What he then did was collect data, lots of data. In his book he describes manual methods he used using amateur players, but the goldmine he had came from the PGA Tour: ShotLink. In 2004, the PGA Tour introduced this new system. At most tournaments in their schedule, it would track the exact position of each shot a player made, including distance to the hole and the lie. With this, Broadie went to work. For each distance to the hole and lie combination, he calculated how many shots did it take for a PGA Tour player on average to get the ball in the hole. With this data in hand, he could create a table:

| Distance (yards) | Lie     | Avg shots |
| ---------------- | ------- | --------- |
| 150              | Fairway | 3.0       |
| 150              | Rough   | 3.2       |
| 450              | Tee     | 4.2       |

 With the example data above, how do we calculate the performance of a shot? Let's say a player is hitting his drive on a 450 yard hole. He hits his drive 300 yards, and it leaves him 150 yards to the hole. If he hit the fairway, it means that his avg shots. left from his positions went from 4.2 to 3.0. Since he used 1 shot to get there, his shot was 4.2 - 3.0 - 1 = 0.2 shots better than average. Had he instead hit it to the rough, his shot would have been 4.2 - 3.2 - 1 = 0.0 compared to average, thus average. With this information in hand, Broadie could create shot categories (drive, approach, pitch/chip, and putt) and add up players performance for all shots in a round to gauge what the player did well or not. For example, if a player's round score was 5 shots better than average for that round, it could be because they putted 5 shots better than average, or because their approach shots were 5 shots better than average, or something in between. To account for course difficulty and the skill of all player's in the tournament, each categorie's score was compared to the average of all player's score for that round. 

This analysis gave players and fans a lot more insights into what a player was doing well, and what they were not doing well. Before this, the fact that someone was a good putter was based more on feeling than anything else, but with this data in hand, it could actually be quantatively shown. 

I made my own analysis of a more granular case using 2018 PGA Tour data [here](https://github.com/PhilipEkfeldt/Golf-Analysis). Sadly the PGA Tour data is no longer available for academics so this will not be possible anymore. 

Additionaly, if you are interested, I would really recommend that you checkout [Data Golf](https://datagolf.org/) as well. They do a lot of interesting analysis as well, usually on a slightly more macro level. 
