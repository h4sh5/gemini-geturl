# gemini-geturl
a simple gemini client that prints the content to stdout and prints found links out to stderr

## usage

using the command line:
```
./gemini-geturl gemini://example.com
```

extract all the links:
```
./gemini-geturl gemini://example.com 2> links
```

loop through links / use as crawler:
```sh
# use a while loop (single threaded)
while read u; do ./gemini-geturl $u; done < links

# use GNU parallel
cat links | parallel ./gemini-geturl {}
```


