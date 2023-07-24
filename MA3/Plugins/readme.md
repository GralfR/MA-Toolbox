# grandM3 - Plugins
This is, where LUA plugins for MA3 might go...
Still work in progress...

# in which seq (Search sequences for fixture)
In lack of a search-feature on MA3 1.9.3.3 this plugin was created to be able to answer the question "where is fixture x used?".
This is especially an important question when working with conventionl fixtures, that need to be focused manually and can't be used for more than one position inside the show.
This is often the case in TV-studios or theaters using conventional fresnel or spots without remote-controlled Pan/Tilt-joke.
On grandMA1 there was the Report-command, that might give a clue, in which sequence the fixture is stored.
On MA2 there came the search-feature, that was much more powerfull than the simple report-function on MA1, but also was implemented very late.
MA3 is missing any of those features at least until version 1.9.3.3 (feature-request is reported, but not terminated, when a search-feature will be implemented).
There are some workarounds to answer the above question including always using presets in any case, so selecting a fixture will light up a preset inside the pool and you will be able to gues, that this fixture might be in use.
If you are using sequences in any case you want to use a fixture to light a scene (yes, MA3 might assign Presets to executors and thus there is no need for a sequence to output a stored look), then this plugin might be usefull for you.
### function:
It runs thru all the sequences inside the selected datapool and reports sequence number and -name if the selected fixture is stored in any cue or part of the sequence. This might help to answer the question "is this fixture used anywhere?".
### limitations:
This plugin only searches sequences (no presets, groups etc.) and can only look for one fixture at a time (might look for several fixtures but then it's hard to distinguish which fixture is used in which sequence). Also only fixture-IDs are supported, no customIDs.
Also cues and parts inside a sequence are not checked/reported. This might be added but in lack of (knowledge of) clean LUA functions this might mess up the commandline history a lot. In my case, there is no need for such deep scan. If it's important to know, in which cue the fixture is stored, just select the sequence and take a look at the tracking sheet. In my case most sequences just have one cue (TV lighting workflow).
### todo/ideas:
Because LUA is documented worst in MA3, it's hard to find the right function/object that might offer the needed data. Thus the plugin uses some commandline-commands, which makes the output very untidy inside the commandline history. This may be cleaned up in the future... 
### alternatives:
If you just need to know, if a selected fixture is stored inside any sequence - without the information, which sequence - then a simple "- seq thru" inside the commandline will to the same job. Result will be: if the fixture is removed from the selection, it's stored in at least one sequence.
