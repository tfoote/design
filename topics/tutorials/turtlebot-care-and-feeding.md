---
layout: tutorial
title: TurtleBot Care and Feeding
reference_id: turtlebot-care-and-feeding
abstract:
  How to charge and maintain your TurtleBot.
tags: [TurtleBot]

provided skills: [charging]
required_skills: [install, network configuration]
---

# {{ page.title }}

* This will become a table of contents (this text will be scraped).
{:toc}

## Power Management

There are two batteries in the TurtleBot, the laptop battery and the mobile base battery (either Create or Kobuki). Each has an independent charging brick and charges independently, you will see the status of both in the TurtleBot dashboard.

## Robot Base

### Kobuki Base or Create Base

The kobuki is much simpler than the create to recharge. You generally don't have to worry about power management (although you can) as the recharger has enough juice to recharge the batteries and keep the robot powered at the same time. This lets you get on with simple experiments like the kinect.

There are two means of recharging, one is via the manual adapter and the second via the docking station.

To set the docking station up, simply take your adapter and plug it into the hole on the inside of the docking station. If you find your adapter is too small to fit inside the docking station just put the adapter to the side and just run the cable through to the inside of the docking station - why? .

## Laptop

The laptop is simple, plug it in and it charges. Make sure to seat the plug completely in the laptop, it will sort of click in.

### Recharging from the Kobuki

If you have a kobuki and a modified recharging cable, you can plug it into the large connector on the left hand side of the kobuki - this will recharge the laptop while the kobuki itself is recharging (either from adapter or docking station).

*Note that it won't recharge while running. This would drain too many amps from the robot that are needed by whatever devices you have mounted on top.*

