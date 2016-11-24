# The Trump Bot
Picks a random line from Trump's Times round-table and uses your browser to speak it.

This came out of a weird idea from back during the primaries which used curl to feed a randomly picked trump line to OSX's `speak` command.   Here's an example using the Times Round-table transcript used for this project:

```
curl -s -b -N --location http://www.nytimes.com/2016/11/23/us/politics/trump-new-york-times-interview-transcript.html \
| perl -0ne 'my @list = $_ =~ m/>TRUMP:(.*?)<\/p>/smg; print $list[rand @list]' \
| say  -i -r 300 -v Alex
```
