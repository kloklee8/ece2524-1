#XSLTOPTIONS=--stringparam generate.toc "nop"
#HOMEWORK_SRCS=homework*.xml
#HOMEWORK_PDF=""
XML = git_intro_assignment.xml
HTML=${XML:.xml=.html}
PDF=${XML:.xml=.pdf}
#VPATH=xml

all: all_html all_pdf

all_html: ${HTML}

all_pdf: ${PDF}

%.fo: %.xml
	xmllint --valid --noout $^
	xsltproc ${XSLTOPTIONS} /usr/share/xml/docbook/stylesheet/docbook-xsl/fo/docbook.xsl $^ > $@

%.html: %.xml
	xmllint --valid --noout $^
	xsltproc ${XSLTOPTIONS} /usr/share/xml/docbook/stylesheet/docbook-xsl/xhtml/docbook.xsl $^ > $@

%.pdf: %.fo
	fop -fo $^ -pdf $@

clean:
	-rm *.fo
