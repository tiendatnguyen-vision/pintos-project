CC=gcc
CFLAGS=-g
OBJECTS=list.o hash.o bitmap.o hex_dump.o testlib.o 
TARGET=testlib

all: $(TARGET)

hex_dump.o: hex_dump.c hex_dump.h round.h
	$(CC) -c hex_dump.c $(CFLAGS)

list.o: list.c list.h
	$(CC) -c list.c $(CFLAGS)

hash.o: hash.c hash.h list.h
	$(CC) -c hash.c $(CFLAGS)

bitmap.o: bitmap.c bitmap.h limits.h round.h
	$(CC) -c bitmap.c $(CFLAGS)

testlib.o: testlib.c testlib.h list.h hash.h bitmap.h hex_dump.h
	$(CC) -c testlib.c $(CFLAGS)

$(TARGET): $(OBJECTS)
	$(CC) -o $(TARGET) $(OBJECTS) $(CFLAGS)

clean:
	rm -rf $(OBJECTS) $(TARGET)