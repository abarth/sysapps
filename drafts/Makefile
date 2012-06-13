ANOLIS = anolis

all: raw-socket.html data/xrefs/sysapps/raw-socket.json

raw-socket.html: raw-socket.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="raw-socket" \
	--filter=".publish, .now3c" $< $@

data/xrefs/sysapps/raw-socket.json: raw-socket.src.html Makefile
	$(ANOLIS) --dump-xrefs=$@ $< /tmp/spec

publish:: raw-socket.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="raw-socket" \
	--filter=".dontpublish, .now3c" --pubdate="$(PUBDATE)" --w3c-status=WD \
	$< raw-socket.html
