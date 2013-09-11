## Purpose

Missions in I&A 3, by default, cover Tactical Missions, Ghost Missions, Priority Targets and Sub-Objectives, though an endless amount of types can be created by developers. While [Main AOs](/Main_AOs/Overview) and [Bases](/Bases/Overview) cover large-scale, destruction-based attacking and defending, missions are designed to give players an opportunity to approach targets more tactically. These missions should be, essentially, mini missions within I&A 3, randomly spawning throughout the map and using the terrain and objects surrounding them to produce a dynamic set of unique objectives that challenges players and makes them think through their play a lot more than they would in other, larger attacks.

In I&A 3, these missions will be essential for expanding the team's arsenal, supplying you with attack vehicles otherwise unobtainable.

## The problem they resolve

[Main AOs](/Main_AOs/Overview) are a great way to handle huge, sprawling attacks and it can be fun to co-operate in the mass destruction. There comes the problem, however, that these AOs become rather boring. Enter missions. Small, squad-based content created for a few players is often hugely enjoyable, but once played almost instantly loses its replayability appeal. The concept is for missions in I&A 3 to take these enjoyable, objective-focused content and make it as dynamic as possible.

With these missions being the only way to acquire attack vehicles, they're essential for the whole team to participate in at one point or another, therefore everyone should get at least a small taste of the tactics.

## How it works

The default missions in I&A 3 will have some basic rules defining each one.

* **Tactical Mission** - A mission where killing everything is a guaranteed failure. Attack vehicles are rewarded for the completion of these missions.
* **Ghost Mission** - A mission where remaining undetected is paramount. Emplacements are rewarded for the completion of these missions.
* **Priority Target** - A time-critical mission that puts all players under threat. Safety is the reward for the completion of these missions.
* **Sub-Objective** - A destruction-based / capture mission that is inside a Main AO but not explicitly marked. Main AOs can not be completed without first completing these missions.



## Customisation

As mentioned briefly above, developers can expand I&A 3 by creating more mission types that suits their needs. Creating a new mission type is documented over at the [Creating a Mission Type](/Missions/Creating_a_Mission_Type) page.

Each mission has its own configuration files, kept in `config/tactical`, `config\priority` and so on. The specification of each can contain elements not present in others, but generally they all require four attributes on top of the classname rule.

1. **Classname** - Should be in [CamelCase](http://en.wikipedia.org/wiki/CamelCase) starting with a lowercase letter, containing nothing but A-Z characters. This will be the unique code for your mission when the system creates markers and the like.
2. **title** - The title of the mission as it will appear on the map and in notifications and hints.
3. **description** - A description of the mission, its rules and how to complete it. Give a little bit of backstory if you can; this will appear in the players' diaries so there's space to read up.
4. **pos** - In string format, either an array or a command should go here. Use of [`AW_fnc_findSpace`](/Functions/Generic/findSpace) is encouraged.

```sqf
class getDocuments
{
	title = "Get Documents";
	description = "Your job is to get papers, like.";
	pos = "[""land"", true, 15] call AW_fnc_findSpace;";
};
```
