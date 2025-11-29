DOL2ELF := dol2elf

DOLLZ3_URL := https://wiibrew.org/w/images/e/ef/Dollz3.zip
DOLLZ3 := dollz3

all: $(DOL2ELF) dollz3

$(DOL2ELF): dol2elf.c
	@echo compiling $< ...
	@$(CXX) -fpermissive -o $@ $<

dollz3.zip:
	@echo downloading $@ ...
	@curl -L $(DOLLZ3_URL) -o $@

dollz3: dollz3.zip
	@echo extracting $@ ...
	@unzip -p $< dollz3/$(DOLLZ3) > $@
	@chmod +x $@

clean:
	@echo "clean ..."
	@rm -f $(DOL2ELF) dollz3 dollz3.zip

.PHONY: all clean
.DELETE_ON_ERROR:
