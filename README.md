http://donaldspeaks.us/

# The Trump Bot
Picks a random line from a given Donal Trump interview transcript and uses your browser to speak it via the new text to speach api. Because his statements sound even nuttier that way.

Periodically I'll update this page to use a different transcript which requires tweaking the regex a little.

## Origins

This came out of a weird idea from back during the primaries which used curl to feed a randomly picked trump line to OSX's `speak` command.   Here's an example of the curl equivalent using the Times Round-table transcript used for this project:

```
curl -s -b -N --location http://www.nytimes.com/2016/11/23/us/politics/trump-new-york-times-interview-transcript.html \
| perl -0ne 'my @list = $_ =~ m/>TRUMP:(.*?)<\/p>/smg; print $list[rand @list]' \
| say  -i -r 300 -v Alex
```
