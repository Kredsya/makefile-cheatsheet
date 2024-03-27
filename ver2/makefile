TARGET=programname
SRCDIR=./src
OBJDIR=./obj
SRCS=$(wildcard $(SRCDIR)/*.c)
OBJS=$(patsubst $(SRCDIR)/%.c, $(OBJDIR)/%.o, $(SRCS))

cFLAGS=-Wall -Wextra -O2 -g
# LDLIBS=-lpcap

all: $(TARGET)

$(OBJDIR):
	mkdir -p $(OBJDIR)

$(OBJDIR)/%.o: $(SRCDIR)/%.c | $(OBJDIR)
	$(COMPILE.c) $(OUTPUT_OPTION) $<

$(TARGET): $(OBJS)
	$(LINK.c) $^ $(LOADLIBES) $(LDLIBS) -o $@

clean:
	rm -rf $(TARGET) $(OBJDIR)