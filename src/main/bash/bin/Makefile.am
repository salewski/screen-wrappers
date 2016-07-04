## Process this file with automake to produce Makefile.in   -*-Makefile-*-

INPUT_TEMPLATES = screen-ls.in


# "static" scripts
SSCRIPTS =
# "generated" scripts (filtered here by do_subst)
GSCRIPTS = screen-ls


# "static" man pages, section 1
S1MANPAGES =
S1MANPAGES_AS_HTML =
# "generated" man pages, section 1
G1MANPAGES = $(INPUT_TEMPLATES:.in=.1)
G1MANPAGES_AS_HTML = $(INPUT_TEMPLATES:.in=.1.html)


ALL_MANPAGES_1 = $(S1MANPAGES) $(G1MANPAGES)

ALL_MANPAGES_1_AS_HTML = $(S1MANPAGES_AS_HTML) $(G1MANPAGES_AS_HTML)


# "static" man pages
SMANPAGES = $(S1MANPAGES)
SMANPAGES_AS_HTML = $(S1MANPAGES_AS_HTML)
# "generated" man pages
GMANPAGES = $(G1MANPAGES)
GMANPAGES_AS_HTML = $(G1MANPAGES_AS_HTML)


bin_SCRIPTS = $(SSCRIPTS) $(GSCRIPTS)

dist_noinst_DATA = $(INPUT_TEMPLATES)

man1_MANS = $(ALL_MANPAGES_1)

man1html_DATA = $(ALL_MANPAGES_1_AS_HTML)


CLEANFILES = $(GSCRIPTS) $(GMANPAGES) $(GMANPAGES_AS_HTML) $(SMANPAGES_AS_HTML)

@do_subst_command@


# Generated files depend on Makefile so they will be rebuilt if $(VERSION) or
# other do_subst'ituted variables change.
$(GSCRIPTS) $(GMANPAGES) $(GMANPAGES_AS_HTML) $(SMANPAGES_AS_HTML): Makefile


# These files depend on Makefile so they will be rebuilt if $(VERSION) or
# other do_subst'ituted variables change. Use chmod a-w to prevent people from
# editing the wrong file by accident.
#
# Note that the script depends on the naming convention:
#
# Target:
#
#     <PROG_NAME_BASE>
#
# is generated from:
#
#     <PROG_NAME_BASE>.in
#
$(GSCRIPTS): % : %.in
	set -e ;\
	rm -f "$@" "$@.tmp" ;\
	_t_base="$@"        ;\
	$(do_subst) "$(srcdir)/$${_t_base}.in" > "$@.tmp" ;\
	mv "$@.tmp" "$@"    ;\
	chmod a-w "$@"      ;\
	chmod a+rx "$@"


# $(G1MANPAGES): %.1 : %.in
$(G1MANPAGES): %.1 : %
	target_name="$@" ;\
	tname=$$(echo "$${target_name}" | sed -e 's/\.1$$//') ;\
	"$(POD2MAN)" $< \
	    --center='User Commands' \
	    --name="$${tname}" \
	    --release=$(PACKAGE)-$(VERSION) \
	    --section=1 > "$${target_name}"


# $(G1MANPAGES_AS_HTML): %.1.html : %.in
$(G1MANPAGES_AS_HTML): %.1.html : %
	target_name="$@" ;\
	tname=$${target_name};\
	"$(POD2HTML)" \
	    --htmlroot='http://example.com/' \
	    --css='../../stylesheets/pod2html-manpage.css' \
	    \
	    --infile='$<'      \
	    --outfile="$${target_name}" \
	    \
	    --title="$${tname}" \
	    \
	    --flush      \
	    --nobacklink \
	    --noheader   \
	    --noindex    \
	    --noquiet    \
	    --verbose


clean-local:
	$(MAKE) clean-generated-man-pages
	$(MAKE) clean-pod2html-cache-files


clean-generated-man-pages:
	set -e ;\
	list='$(GMANPAGES)' ;\
	for mpath in $${list}; do \
	    $(RM) -f "$${mpath}" ;\
	    test $$? -eq 0 || exit 1 ;\
	done


# In theory, this should not be necessary, but it is required for the author
# using pod2html from the Debian package perl-5.20.2-3+deb8u5
#
# See also:
#
#     https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=616582
#     https://rt.perl.org/Public/Bug/Display.html?id=69782
#
clean-pod2html-cache-files:
	$(RM) -f -v pod2htmd.tmp pod2htmi.tmp


PHONY = \
    clean-local \
    clean-generated-man-pages \
    clean-pod2html-cache-files
