---
layout: post
title:  "A look at a decade of NBA basketball"
date:   2019-12-31 15:00 +0100
tags: [data, visualization, basketball ]
---

Another decade of NBA basketball has gone by. Let's look at some data! To start with, here are charts showing the top 30 leaders in the most common statistics. See the end of this page for more information on how all of this was made.

### Top 30 Points

{%include img-link.md img='images/2019-12-31/Top 30 scorers.png'%} 
### Top 30 rebounds

{%include img-link.md img='images/2019-12-31/Top 30 rebounders.png'%} 
### Top 30 assists

{%include img-link.md img='images/2019-12-31/Top 30 assists.png'%} 
### Top 30 blocks

{%include img-link.md img='images/2019-12-31/Top 30 blocks.png'%} 
### Top 30 steals

{%include img-link.md img='images/2019-12-31/Top 30 steals.png'%} 
### Top 30 fouls

{%include img-link.md img='images/2019-12-31/Top 30 fouls.png'%} 
### Top 30 turnovers

{%include img-link.md img='images/2019-12-31/Top 30 turnovers.png'%} 
### Top 30 free throw attempts

{%include img-link.md img='images/2019-12-31/Top 30 FTA.png'%} 

There are some conclusions to be drawn:
- James Harden is a generational scoring talent and incredibly adept at getting to the free throw line.
- Serge Ibaka is a somewhat surprising leader in the blocks category, especially considering he played at power forward for most of his career. It shows that there were few great centers in this decade.
- Chris Paul is just 80 assists shy of Russell Westbrook's total, but has less than half of Westbrook's number of turnovers.

These are the players that managed to score more than 10000 points, grouped by position:

{%include img-link.md img='images/2019-12-31/Top scorers of the decade by position.png'%} 

The current generation of stars doesn't just put up points, they do it while being extremely efficient. James Harden, LeBron James, Kevin Durant and Stephen Curry all managed to score 15,000 points on at least 60 TS%.

To get a good overview on how they relate to the rest of the NBA, have a look at this scatter plot:

{%include img-link.md img='images/2019-12-31/Top scorers of the decade (scatter).png'%} 

The median number of points scored over the last 10 years per player is "barely" 3320.

Here is the same plot, but then compared to true shooting percentage, of players that scored more than 1000 points:

{%include img-link.md img='images/2019-12-31/Top scorers of the decade (scatter)_ts.png'%} 

Russell Westbrook has scored a large number of points, but compared to his former OKC teammates, James and Curry he does it a lot less efficiently. And yes, Lonzo Ball doesn't only score few points, he does it while being the second least efficient scorer of the last decade!

Another favorite metric of mine is assists vs. turnovers. This scatter plot shows us which players score the highest in this ranking:

{%include img-link.md img='images/2019-12-31/AST_TO.png'%}

Things I notice:

- Chris Paul truly is a point god. 
- DeMarcus Cousins averages a lot of turnovers, but at least he also manages to rack up a decent number of assists.
- Dwight Howard (whose data point is unlabeled, but I'm sure you can spot him), also has a ton of turnovers, and has no assists to make up for it. 
- Marc Gasol has a better AST/TO ratio than most shooting guards. Frankly, I think he's one of the most overlooked players and has a case for being the best center of the decade.  


### The rise of the three point shot

To say that the way the game is played differently compared to just 10 years ago would be an understatement. This plot shows the ratio of three point shots being taken compared to two point shots and the percentage at which those shots are made:

{%include img-link.md img='images/2019-12-31/3fg ratio.png'%}

The evolution is staggering, and most surprisingly: the efficiency does not suffer. As long as players don't stop making the shots, there is no reason why this trend should stop. 

Another evolution is that players play less minutes, and that most of their energy is saved for the playoffs. Again, the numbers don't lie: while the average starter would average almost 32 minutes per game, today the average starter only plays 30.4 minutes. In the 2017-2018 season, they barely got above 30 minutes per game.

{%include img-link.md img='images/2019-12-31/Average mpg for starters.png'%}

The trend becomes even more clear when we also look at the previous decade:

{%include img-link.md img='images/2019-12-31/Average mpg for starters_2003.png'%}

Between 2003 and 2019, the average starter lost almost 4 minutes of game time!

### Colleges

What colleges are responsible for producing the most NBA players? The following plot shows who takes the crown:

{%include img-link.md img='images/2019-12-31/Colleges by number of picks.png'%}

Kentucky is the clear winner here, having produced 38 NBA players between 2010 and 2019, including names such as Anthony Davis, Devin Booker, Karl-Anthony Towns and John Wall. The second and third spot are taken by Duke and Kansas.

Perhaps you wonder if quality equals quantity? Have a look at which colleges have the highest average draft picks:

{%include img-link.md img='images/2019-12-31/Colleges with average draft pick.png'%}

The ranking seems fairly well respected. The surprisingly successful colleges here are Oklahoma and Ohio State, who only have a few graduates playing in the NBA, but these include highly ranked picks such as Trae Young, Buddy Hield, D'Angelo Russell and Blake Griffin (who was technically drafted in 2009, but is considered to have started his career in 2010 since his missed his first season.)

## Attribution

These charts were made using:
- (scraped) data from Basketball Reference
- Tableau data visualization software

Note that the data includes everything starting from the 2010/2011 season up until 27/12/2019, which is technically not the whole decade, but it's good enough for me.
