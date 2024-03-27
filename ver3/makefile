TARGET=programname
SRCDIR=./src
SRCHDRDIR=./src/subfolder
OBJDIR=./obj
OBJHDRDIR=./obj/subfolder
SRCS=$(wildcard $(SRCDIR)/*.c) $(wildcard $(SRCHDRDIR)/*.c)
OBJS=$(patsubst $(SRCDIR)/%.c, $(OBJDIR)/%.o, $(SRCS))

CPPFLAGS=-Wall -Wextra -O2 -g
# LDLIBS=-lpcap

all: $(TARGET)

$(OBJDIR):
	mkdir -p $(OBJDIR) $(OBJHDRDIR)

$(OBJDIR)/%.o: $(SRCDIR)/%.c | $(OBJDIR)
	$(COMPILE.cpp) $(OUTPUT_OPTION) $<

$(TARGET): $(OBJS)
	$(LINK.cpp) $^ $(LOADLIBES) $(LDLIBS) -o $@

clean:
	rm -rf $(TARGET) $(OBJDIR)