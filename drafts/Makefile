ANOLIS = anolis

.PHONY: publish

all: raw-sockets.html data/xrefs/sysapps/raw-sockets.json runtime.html data/xrefs/sysapps/runtime.json security.html data/xrefs/sysapps/security.json

raw-sockets.html: raw-sockets.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="raw-sockets" \
	--filter=".publish, .now3c" $< $@

data/xrefs/sysapps/raw-sockets.json: raw-sockets.src.html Makefile
	$(ANOLIS) --dump-xrefs=$@ $< /tmp/spec

runtime.html: runtime.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="runtime" \
	--filter=".publish, .now3c" $< $@

data/xrefs/sysapps/runtime.json: runtime.src.html Makefile
	$(ANOLIS) --dump-xrefs=$@ $< /tmp/spec

security.html: security.src.html data Makefile
	$(ANOLIS) --output-encoding=ascii --omit-optional-tags --quote-attr-values \
	--w3c-compat --enable=xspecxref --enable=refs --w3c-shortname="security" \
	--filter=".publish, .now3c" $< $@

data/xrefs/sysapps/security.json: security.src.html Makefile
	$(ANOLIS) --dump-xrefs=$@ $< /tmp/spec

publish:
	git push origin origin/master:gh-pages
