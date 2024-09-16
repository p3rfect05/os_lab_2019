CC=gcc
CFLAGS=-I.

all: sequential_min_max parallel_min_max run_sequential_min_max

sequential_min_max : utils.o find_min_max.o utils.h find_min_max.h
	$(CC) -o sequential_min_max find_min_max.o utils.o sequential_min_max.c $(CFLAGS)

parallel_min_max : utils.o find_min_max.o utils.h find_min_max.h
	$(CC) -o parallel_min_max utils.o find_min_max.o parallel_min_max.c $(CFLAGS)

utils.o : utils.h
	$(CC) -o utils.o -c utils.c $(CFLAGS)

find_min_max.o : utils.h find_min_max.h
	$(CC) -o find_min_max.o -c find_min_max.c $(CFLAGS)

run_sequential_min_max: run_sequential_min_max.c
	$(CC) -o run_sequential_min_max run_sequential_min_max.c $(CFLAGS)

clean :
	rm utils.o find_min_max.o sequential_min_max parallel_min_max run_sequential_min_max

task1:
	./sequential_min_max 1 15
	./sequential_min_max 3 10

task2:
	 ./parallel_min_max --seed 1 --array_size 100000 --pnum 2 --by_files

task3:
	 ./parallel_min_max --seed 1 --array_size 100000 --pnum 3

task4:
	make all

task5:
	# TODO
