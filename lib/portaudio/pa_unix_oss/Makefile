# Make PortAudio Library for Unix/OSS

CC = gcc
srcdir=.

DIRS=../pa_common

override CFLAGS += -g -O -I$(srcdir)/../pa_common
PASRC = $(srcdir)/../pa_common/pa_lib.c $(srcdir)/pa_unix_oss.c $(srcdir)/pa_unix.c
PAINC = $(srcdir)/../pa_common/portaudio.h
PAOBJ = ../pa_common/pa_lib.o pa_unix_oss.o pa_unix.o

portaudio.a: $(PAOBJ)
	ar ruv portaudio.a $(PAOBJ)
	ranlib portaudio.a
#	cp portaudio.a $(DEST)

clean:
	rm -f portaudio.a $(PAOBJ)

distclean: clean

$(PAOBJ): %.o: $(srcdir)/%.c $(PAINC) Makefile $(DIRS)
	$(CC) -c $(CFLAGS) $< -o $@

$(DIRS):
	mkdir $(DIRS)
