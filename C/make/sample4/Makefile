# Makefile
#
# $@	ターゲット名
# $^	すべての必須項目
#

CC		=	gcc -Iinclude
OBJS	=	main.o cmp.o libline.a libmysort.a

vpath %.c src
vpath %.h include

main: $(OBJS)
	$(CC) -o $@ $^

.c.o:
	$(CC) -c $<

main.o: main.c

libline.a: line.o alloc.o
	ar rv $@ $^
line.o: line.h line.c alloc.h
alloc.o: alloc.h alloc.c

libmysort.a: mysort.o swap.o
	ar rv $@ $^
mysort.o: mysort.h mysort.c swap.h
swap.o: swap.c swap.h

cmp.o: cmp.h cmp.c


# "clean" というファイルがあっても、擬似ターゲットとして扱う
.PHONY: clean
clean:
	rm -f *.o *.a main
