LIB=../libsrc/libdocmgr.a
PROG=build-bib
CXXFLAGS=-g -I../libsrc
LDFLAGS=-L../libsrc
LIBS=-ldocmgr -lsqlite3

SRCS=build-bib.cpp

OBJS=$(addprefix obj/,$(SRCS:.cpp=.o))

all: obj $(PROG)

obj:
	if [ ! -d obj ]; then mkdir obj ; fi

build-bib: $(OBJS)
	$(CXX) -g $(LDFLAGS) -o $@ $^ $(LIBS)

depend:
	makedepend -Y -pobj/ -- $(CXXFLAGS) -- $(SRCS) 2> /dev/null

clean:
	rm -f build-bib $(OBJS)

obj/%.o: %.cpp
	$(COMPILE.cpp) -o $@ $<


# DO NOT DELETE THIS LINE -- make depend depends on it.

obj/build-bib.o: ../libsrc/DocMgr.hh
