TARGET = example
LIBS = ../../../../client_libraries/c/lib/libsparkplug_b.a -Llib -L/usr/local/lib -lmosquitto
CC = gcc
CFLAGS = -g -Wall -I../../../../client_libraries/c/include/

.PHONY: default all clean

default: $(TARGET)
all: default

OBJECTS = $(patsubst %.c, %.o, $(wildcard *.c))
HEADERS = $(wildcard *.h)

%.o: %.c $(HEADERS)
	$(CC) $(CFLAGS) -c $< -o $@

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	$(CC) $(OBJECTS) -Wall $(LIBS) -o $@

clean:
	-rm -f *.o
	-rm -f $(TARGET)
