all: id3v2

ID3=/home/sasl/shared/main3/env/tools

CC=g++  #nom du compilateur
CFLAGS=-Wall  #option de compilation
LDLIBS=-lid3 -lz #bibliotheques à lier

CH=/home/sasl/eleves/main/3407501/TP_solo



convert.o: convert.cpp
	${CC} -I ${ID3}/include -DVERSION="\"${VERSION}\"" -c -o convert.o convert.cpp

list.o: list.cpp
	${CC} -I ${ID3}/include -DVERSION="\"${VERSION}\"" -c -o list.o list.cpp


genre.o: genre.cpp
	${CC} -I ${ID3}/include -DVERSION="\"${VERSION}\"" -c -o genre.o genre.cpp

id3v2: convert.o list.o id3v2.o genre.o
	${CC} -L ${ID3}/lib ${CFLAGS} -o id3v2 $@ ${LDLIBS}
install:
	mkdir ${CH}/bin ${CH}/man ${CH}/man/man1
	cp ${CH}/EnvDev/id3v2-0.1.11/src/id3v2 ${CH}/bin
	nroff -man ../id3v2.1 > ${CH}/man/man1/id3v2.1

clean: 
	rm *.o id3v2

distclean:
	rm  ${CH}/man/man1/id3v2.1

