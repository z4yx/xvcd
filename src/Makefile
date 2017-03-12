O ?= .
OBJ ?= $(O)/obj
CFLAGS=-Werror -Wall -Os -g
LDFLAGS=-lftdi1

all: $(O) $(O)/xvcd

.PHONY: $(O) $(OBJ)

$(O):
	mkdir -p $(O)

$(OBJ):
	mkdir -p $(OBJ)

$(O)/xvcd: $(OBJ)/io_ftdi.o $(OBJ)/xvcd.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

$(OBJ)/%.o: %.c $(OBJ) io_ftdi.h
	$(CC) -c $< -o $@ $(CFLAGS)
