# Welcome to vSpy!
**WARNING:  vSPY IS UNDER ACTIVE DEVELOPMENT**

vSpy is a simple Java application that interfaces with AutoHotKey and LuaMacros to use modifier-key key combinations to control vMix.  vMix only allows you to create keyboard shortcuts with single keys.  Unfortunately, this makes them pretty useless, because you need to keep your single keys open for things like, you know, typing.  vSpy allows you to bypass this "shortfall" of vMix to control vMix with a keyboard.

### Basic Program Flow

There are two ways you can use vSpy.  ~~If you wish, you can simply use vSpy as a standalone program.~~  For more advanced users who need a proper control surface for vMix, I recommend using it with AHK and LuaMacros.

#### vSpy + AHK + LuaMacros

LuaMacros is a program that allows you to accept input from only one specific keyboard and process it through a script.  Normally, Windows views all keyboards as one.  LuaMacros overcomes this so you can have additional keyboards acting as dedicated control surfaces.

LuaMacros does some magic things (*documentation coming soon*) to send keystrokes to AHK, which can be mapped to take those keystrokes and send full key combinations accordingly.

vSpy listens for keyboard combinations sent by AHK, and if the keyboard combination is mapped in the vSpy configuration, the appropriate command gets sent to vMix through its Web API.

#### ~~Standalone vSpy~~ [NOT YET AVAILABLE]

~~Configure vSpy according to your wishes (*documentation coming soon*) and start it up.  You now can use keyboard combinations to control vMix.  (*again, documentation coming soon*)~~

*The reason this isn't available yet is because currently AHK has to send an `{F23 down}` command to tell vSpy to start logging keys in its buffer, and it keeps logging keys until AHK sends `{F23 up}`.  This is obviously poor design and will eventually be fixed.  When that is fixed, it will be possible to use vSpy without tying it to LuaMacros and AHK.*

### Performance Considerations

Let's be honest.  This is hacky software.  I can't make any performance guarantees.  You're taking 3 standalone pieces of software and lashing them together to control a fourth.  There are no guarantees when you do that.  What I CAN say, however, is that it has worked very well for me in my tests and control flow shows almost zero latency (*read: I can't detect **any** latency, but I don't want to definitively say it's "zero latency", because surely that's not actually technically true*)

### Software Updates

vSpy will (probably) be continually getting updates.  Here is roughly my list of priorities (from highest to lowest):

1) Getting it published and usable by "super users".
2) Adding some logic in the AHK and LuaMacros scripts to support multiple additional keyboards (currently you can only have one macro keyboard.  This is primarily an artifact of how the LuaMacros script is set up, but in order to actually support multiple extra keyboards in our system, the AHK script will need some retrofitting.)
3) Getting the configuration cleaned up a bit so anyone can comfortable use it
4) Rewriting the key buffer logic in vSpy so it doesn't need AHK to send it an activation key (see "Standalone vSpy" paragraph above)
5) Rewriting the AHK and LuaMacros scripts so they aren't an absolute atrocity.

To be completely honest, I can't guarantee the project will progress past #1.  I only need it to get to #1 for my uses, so I probably won't be overly motivated to spend time continuing development unless there is demand for it.  If there is "sufficient demand", however, I will absolutely continue development.

### Community Contributions

If you're interested in contributing to this project, you're absolutely welcome to!  This software is hacky (partially by nature...partially because I don't know what I'm doing), so if you want to help make it not hacky, your contributions are more than welcome.  I'm not going to be putting together any contributor guidelines here at the outset, so if you want to contribute, it would be appreciated if you contact me first.  Alternatively, you could just file the pull request and hope I don't fail the code review.  Up to you.  Either way, I promise I don't bite.  Even if I did, it's kind of hard to bite someone across the internet, so you're probably safe regardless.
