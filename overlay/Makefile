DTS_FILES = $(wildcard *.dts)
DTBO_FILES = $(patsubst %.dts,%.dtbo,$(DTS_FILES))
DTS_COMPILED_FILES = $(patsubst %.dts,%.dts.compiled,$(DTS_FILES))

all: $(DTBO_FILES)

dts_compiled: $(DTS_COMPILED_FILES)

%.dtbo: %.dts
	dtc -@ $^ -o $@

%.dts.compiled:  %.dts
	dtc -@ $^ -O dts -o $@

.PHONY: clean

clean:
	rm -f *.dtbo *.dts.compiled