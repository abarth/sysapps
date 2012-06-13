ANOLIS = anolis

all: raw-sockets.html data/xrefs/sysapps/raw-sockets.json

raw-sockets.html: raw-sockets.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="raw-sockets" \
	--filter=".publish, .now3c" $< $@

data/xrefs/sysapps/raw-sockets.json: raw-sockets.src.html Makefile
	$(ANOLIS) --dump-xrefs=$@ $< /tmp/spec

publish:: raw-sockets.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="raw-wsockets" \
	--filter=".dontpublish, .now3c" --pubdate="$(PUBDATE)" --w3c-status=WD \
	$< raw-sockets.html
