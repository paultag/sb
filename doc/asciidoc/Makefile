#
# create manpages from the asciidoc files
#

SRC1 = sb-create.txt sb-login.txt sbo.txt sb-prehook.txt sb-update.txt \
	   sb-endsession.txt sb-maint.txt sb-posthook.txt sb.txt

MAN = $(SRC1:.txt=.1)
DISTFILES = $(addprefix ../,$(MAN))

all: $(MAN)

dist: $(DISTFILES)

clean:
	rm -fv $(MAN)

%.1 : %.xml
	xmlto man $<

%.5 : %.xml
	xmlto man $<

../%.1: %.1
	cp $< $@

../%.5: %.5
	cp $< $@

%.xml : %.txt
	asciidoc -b docbook -d manpage -o $@ $<
