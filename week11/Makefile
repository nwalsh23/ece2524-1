SRC := main.cpp iodat.cpp
OBJ := ${SRC:.cpp=.o}
LIBS := -lboost_program_options
CC := g++
CFLAGS := -Wall -g -std=c++0x

main: ${OBJ}
	${CC} ${CFLAGS} -o $@ ${LIBS} ${OBJ}

#generate dependancy files at the same time as object compilation
%.o : %.cpp
	${CC} ${CXX_FLAGS} -MD -o $@ -c $< 
	@cp $*.d $*.P; \
	  sed -e 's/#.*//' -e 's/^[^:]*: *//' -e 's/ *\\$$//' \
	 	  -e '/^$$/ d' -e 's/$$/ :/' < $*.P >> $*.d; \
	  rm -f $*.P

clean:
	-rm *.o *.d *~

archive:
	tar -cvzf FinalProject1.tar.gz *.cpp *.h Makefile README

