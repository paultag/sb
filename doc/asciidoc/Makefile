#
# create manpages from the asciidoc files
#

SRC1 = sb-create.txt sb-login.txt sbo.txt sb-prehook.txt sb-update.txt \
	   sb-endsession.txt sb-maint.txt sb-posthook.txt sb.txt

SRC5 = sb-layout.txt

MAN1 = $(SRC1:.txt=.1)
MAN5 = $(SRC5:.txt=.5)
DISTFILES1 = $(addprefix ../,$(MAN1))
DISTFILES5 = $(addprefix ../,$(MAN5))

all: $(MAN1) $(MAN5)

dist: $(DISTFILES1) $(DISTFILES5)

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
