

default: program
	gcc -o program program.c number.c

program: libnumber.so program.o program.c 
	gcc -c -o program.o -fPIC program.c
	gcc -o program program.o -lnumber -L.
	
libnumber.so : number.o number.h
	gcc -o libnumber.so -shared number.o

number.o : number.h number.c
	gcc -c -o number.o -fPIC number.c

clean:
	rm -f number.o program.o

distclean: clean
	rm -f libnumber.so program

test: program
	$(PWD)/program
	echo $(val)
