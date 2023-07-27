# MA3: Search Fixture (Search sequences for fixture)
## Introduction
In lack of a search-feature on MA3 1.9.3.3 this plugin was created to be able to answer the question "where is fixture x used?".
This is especially an important question when working with conventionl fixtures, that need to be focused manually and can't be used for more than one position inside the show.
This is often the case in TV-studios or theaters using conventional fresnel or spots without remote-controlled Pan/Tilt-joke.
On grandMA1 there was the Report-command, that might give a clue, in which sequence the fixture is stored.
On MA2 there came the search-feature, that was much more powerfull than the simple report-function on MA1, but also was implemented very late.
MA3 is missing any of those features at least until version 1.9.3.3 (feature-request is reported, but not terminated, when a search-feature will be implemented).
There are some workarounds to answer the above question including always using presets in any case, so selecting a fixture will light up a preset inside the pool and you will be able to gues, that this fixture might be in use.
If you are using sequences in any case you want to use a fixture to light a scene (yes, MA3 might assign Presets to executors and thus there is no need for a sequence to output a stored look), then this plugin might be usefull for you.
But keep in mind: This plugin was created for a special installation as a workaround for the missing search-feature of MA3. It's not intended to work in any situation or fit to any workflow. So don't expect it to be a plug&play-plugin. Maybe it needs some adaption for your special workflow.

## Function
It runs thru all the sequences inside the selected datapool and reports sequence number and -name if the selected fixture is stored in any cue or part of the sequence. This might help to answer the question "is this fixture used anywhere?".

## Usage
Using the plugin may start in two ways.
1. Select a fixture, then start the plugin. It will use the current selection.

-or-

2. Start the plugin without any fixtures selected. Then the plugin will first ask for a fixture-number by a dialog.
### result
The result will be given in a dialog like this:

![in which seq](https://github.com/GralfR/MA-Toolbox/assets/66326427/1d8476fc-9195-42ac-81ff-1d4f0537f62a)
### runtime
Depending on the amount of sequences inside the pool, the time the plugin needs to search all sequences, differs. A progressbar will be shown.

## Limitations
* This plugin only searches sequences (no presets, groups etc.) inside the selected datapool.
* It can only look for one fixture at a time (might be adapted to look for several fixtures but then it's hard to distinguish which fixture is used in which sequence).
* Only fixture-IDs are supported, no customIDs.
* If the current selection has more than one fixture, the first fixture inside the selection will be used.
* Individual cues and parts inside a sequence are not reported in detail. This might be added but in lack of (knowledge of) clean LUA functions this might mess up the commandline history a lot. In my case, there is no need for such deep scan. If it's important to know, in which cue the fixture is stored, just select the sequence and take a look at the tracking sheet. In my case most sequences just have one cue (TV lighting workflow).
* The result is only shown in a dialog like in the picture above. The result can not be used for other commands or stored or copied to other users or anything like that.

## Todo/ideas
Because LUA is documented worst in MA3, it's hard to find the right function/object that might offer the needed data. Thus the plugin uses some commandline-commands, which makes the output very untidy inside the commandline history. This may be cleaned up in the future... 

## Alternatives
If you just need to know, if a selected fixture is stored inside any sequence - without the information, which sequence - then a simple "- seq thru" inside the commandline will to the same job. Result will be: if the fixture is removed from the selection, it's stored in at least one sequence.

## (known) Bugs
It's not tested with subfixtures.
Because this plugin was created for a specific installation there might occur some errors in your special situation. Feel free to take a look at the sourcecode - if you are used to LUA - and fix it yourself.
Or you may open an issue. Maybe I find some time to fix it, but don't expect a 24/7-support. This tool is provided as is.

# ! WARNING !
The programmer is cleared by the plugin! So store things first, if needed!
If the plugin breaks because of any error, the progressbar might not be closed and stick on the screen. I have no clue how to remove it other than with a restart of the console. So test the plugin first and don't use it in live-situations! No warranty given!
