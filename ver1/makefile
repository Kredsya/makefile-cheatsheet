TARGET=programname
SRCDIR=./
SRCS=$(wildcard $(SRCDIR)/*.c)
OBJS=$(patsubst $(SRCDIR)/%.c, ./%.o, $(SRCS))

cFLAGS=-Wall -Wextra -O2 -g
# LDLIBS=-lpcap

all: $(TARGET)

./%.o: $(SRCDIR)/%.c
	$(COMPILE.c) $(OUTPUT_OPTION) $<

$(TARGET): $(OBJS)
	$(LINK.c) $^ $(LOADLIBES) $(LDLIBS) -o $@

clean:
	rm -rf $(TARGET) *.o