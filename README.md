docker-graphviz
================

While trying to generate dependency graphs with [snakefood](https://pypi.org/project/snakefood/) on OSX, I grew frustrated with graphviz not rendering PNG and JPG files properly (I have a bunch of other projects running on my machine).

To avoid all this, I now run `dot` commands within a container instead

To run dot examples like [snakefood's 30 second usage instructions](http://furius.ca/snakefood/doc/snakefood-doc.html#seconds-usage-instructions)
to JPG:
```
sfood /myproject | \
sfood-graph | \
docker run -i -v `pwd`:/data enigma3319/graphviz-runner dot -Tjpg -o /data/example.jpg
```
