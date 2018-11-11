FLAGS=`pkg-config --cflags --libs libdrm`
FLAGS+=-Wall -O0 -g
FLAGS+=-D_FILE_OFFSET_BITS=64

CC=$(CROSS_COMPILE)gcc

all:
	$(CC) -o modeset modeset.c $(FLAGS)
	$(CC) -o modeset-double-buffered modeset-double-buffered.c $(FLAGS)
	$(CC) -o modeset-vsync modeset-vsync.c $(FLAGS)

clean:
	rm -rf modeset modeset-double-buffered modeset-vsync

install: all
ifneq ($(DESTDIR),)
	sudo cp modeset modeset-double-buffered modeset-vsync $(DESTDIR)
endif
