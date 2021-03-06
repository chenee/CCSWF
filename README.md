CCSWF
=====
CCSWF is an attempt to bring Flash interfaces to Cocos2D 1.x (may be easily ported to Cocos2D 2.0 and Cocos2Dx). CCSWF is based on Thatcher Ulrich's [gameswf][1].

What is CCSWF's state?
----------------------
Although CCSWF is in a somewhat usable state, it is a long way from a full production state. Use at your own risk. Since CCSWF is currently based upon gameswf it inherits any of its original limitations, visit the [gameswf website][1] for more info. A lot of testing needs to be done to get CCSWF to a stable release, please report any issues or contribute to make it better.
Touch input and transformations have not been tested on all devices. -Report problems

* Masking is not working. -Do not report this.
* Sound is not working, -Do not report this.
* As with gameswf only ActionScript 2.0 is supported (make sure to publish your SWF files with ActionScript 2.0)
* Scaling the movie breaks the touches TODO

Are there plans for the future?
-------------------------------
Yes. CCSWF was created as a POC of what issues can be solved with flash, namely the biggest bottleneck for many companies: GUI. There are commercial tools like [Autodesk's Scaleform][2] that demonstrate the reach of a tool like this. Also, Adobe has released the [SWF file format spec][3] which opens up the possibilities for many improvements.
CCSWF final goal would be to move away from gameswf and implement a native interface that parses the SWF file and renders it using only Cocos2D classes like CCSprite or CCAction and a couple custom ones for vector graphics. Yet again, that is a long way from becoming a reality.

How does it work?
-----------------
In its current state CCSWF wraps gameswf in a CCSWFNode class that inherits from CCNode. In other words, create an instance of CCSWFNode using code like:

	CCNode *swf = [CCSWFNode nodeWithSWFFile:[[NSBundle mainBundle] pathForResource:@"HelloWorld" ofType:@"swf"]];
	[self addChild:swf];

That's it, you can *almost* treat your CCSWFNode as any other CCNode.

How can I contribute?
---------------------
All fixes/improvements are welcome, there are a couple things that we would like to get people to help with though:

   * ActionScript 3.0 support
   * Native Objective-C SWF parsing
   * Use the Cocos2D scene graph to render the SWF hierarchy
   * Documentation

There are two versions of CCSWF:

   * gameswf backed (currently in a somewhat working state), you can find this version on master
   * Objective-C native (currently not working, uncompressing and initial parsing is complete), you can find this version on the "Objective-C" branch
	



[1]: http://tulrich.com/textweb.pl?path=geekstuff/gameswf.txt "gameswf"
[2]: http://gameware.autodesk.com/scaleform "Autodesk Scaleform"
[3]: http://www.adobe.com/devnet/swf.html "Adobe Devnet - SWF"
