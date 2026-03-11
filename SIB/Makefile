PMC = PMC-SIB-SOICS-00001-01_000-01_ZH-TW.XML
PDF = SIB.pdf
FLAT = SIB-flat.xml
FLAT2 = SIB-flat2.xml

PARAMS += -param include.pmentry.bookmarks 0
PARAMS += -param ulink.show 0
PARAMS += -param generate.table.of.contents 1
PARAMS += -param generate.title.page 1
PARAMS += -stringparam font.family 'Arial,Kai'

all: $(PDF)

$(PDF): $(FLAT2)
	s1kd2pdf -c /app/workspace/ietm_csdb/SIB/fop.xconf -o $(PDF) $(FLAT2) $(PARAMS)

$(FLAT2): $(FLAT)
	xmllint --noent $(FLAT) > $(FLAT2)

$(FLAT): $(PMC) $(wildcard DMC-*.XML)
	s1kd-flatten -d . $(PMC) > $(FLAT)

clean:
	rm -f $(PDF) $(FLAT) $(FLAT2)
