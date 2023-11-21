# The AIMLAC Solution Deployer

-

## Motivation

- You need to place bids every day
- You need to run code to do this
- You don't (yet) know how to deploy to a server to do this automatically

Script:
As we discussed in Cardiff, you will need to devise a strategy to bid on the day-ahead market in a way that will maximise the amount of money the AIMLAC HQ makes on its renewables (or at least minimises the amount it spends on energy in general), and implement this strategy in software. Since this will depend on up-to-date information on weather and market conditions, you will want to run this every day to place the bid for the following market day. Usually you would set up a machine (physical, virtual, or most likely in the cloud) to do this automatically, rather than needing to remember to log in every day to poke the right button. But we won't be covering how to do this kind of thing until Bristol in January, and once we've covered it it may still take you some time to get that set up. So that you can get bids submitting ASAP, we have set up a solution to help.

-

## Starter repository

- One repository per team
- Each has a slightly different strategy
- Each can
  - Fetch the latest market price from our API
  - Construct a valid bid for the following market day
  - Submit the bid to the API
- Pull requests are automatically merged

Script:
For each team we've created a starter repository. These are all based on the same template, but each has a slightly different strategy for how to prepare the bid. However, each one is able to fetch the latest market prices from the API, construct a valid bid for the following market day using some strategy, and submit this bid to the API. We won't give you push access to this repository, but will give you read access, so you can fork it. The repository will automatically merge any pull requests you make to it from your fork, so you can adjust the strategy whenever you need to.

-

## The Runner

- Between 8:30 and 9am UTC each day, the runner
  - Clones each team's repository
  - Installs the package inside an Anaconda Docker container
  - Runs the solution
  - Reports status to Slack
- Time limit of 120s for installation and running
- Fraction of a CPU available

Script:
At some point between 8:30 and 9am UTC each day, the runner will clone a copy of your team's repository, and install the package in the repository inside an Anaconda Docker container. This means you get access to all the packages provided by Anaconda; any other packages will need to be installed, which will take some time. Once the installation is done, it runs your solution, and reports the status to Slack. If it fails, you get full log messages; otherwise you just get a success message and an indication of timing. From the start of installation to the time the program exits your solution is allowed 120s; if it exceeds this it is killed, and a bid may not be submitted. The computational power available is relatively modest&mdash;a fraction of a CPU&mdash;so if your models become non-trivial then you will want to start thinking about deploying your solution to the cloud instead. (Note that the runner doesn't care about pull requests; it runs on its own schedule, with whatever code has been merged into the GitHub repository at that time.)

-

## The Leaderboard

- The market provides a leaderboard
- Teams are ranked by the amount of profit/loss
- Available at [http://sa2c-cirunner.swansea.ac.uk/dashboard/](http://sa2c-cirunner.swansea.ac.uk/dashboard/)
  - Username: `CDT`
  - Password: `CCV5`

Script:
To make things a bit more interesting and let you gauge your progress against the rest of the cohort, we've created a leaderboard to see which team's strategy and deployment perform the best. You can see the total profit/loss for the challenge for each team, and a history of how that has progressed. Your client provided you with a starting budget of £12k. If this drops to zero, you're out.
