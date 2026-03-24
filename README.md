glktermw is a fork of the original glkterm library by Andrew
Plotkin. glktermw supports unicode characters whereas the original is
limited to latin1.

This is my (Steve Horan) personal fork of glktermw with a handful of
quality-of-life modifications. These modifications were done to work
on my system (FreeBSD) but I suspect they should work on most modern
UNIXes, but I make no guarantees.

I am also about as far as one can get from a competent C coder. I
wrestled until I made it do what I wanted, but someone with more
experience probably would've done it better.aIf this is you, please
fork this and clean it up, a more modern and feature-rich glk library
for terminals would be wonderful.

My changes/additions/modifications:

* home/end keys move to the start and end of input line rather than
  scrollback.
* delete key is now treated differently to backspace and deletes the
  character under cursor like expected.
* Basic tab completion
    * Only considers first match
    * First looks for candidates in input history
    * Failing that, searches in most recent 100 lines of scrollback
* CTRL+W does readline style word deletion.
* ALT+F/ALT+B now does readline style forward/back by a word
* keycode_AltPlus now exists for easy ALT+X key triggers
* Unknown key error messages now include key value
* Added an option (See SOUND line in Makefile) to allow you to trick
  terps into thinking they support sound. I had a reason to want this,
  you probably don't, so keep it commented out unless you also have a
  reason.

Things I'd like to do/see someone else do:

* Actually add sound support. Gargoyle's SDL sound support is ripe for
  the stealing here.
* Make it possible to move the status line from the top of screen to the
  bottom. (I'm of the understanding this is largely dictated by the game,
  not glktermw, so this would probably be a kludge at best)

Hopefully these mods will appeal to at least one person out there and
make their terminal-based text-adventuring slightly more pleasant.

