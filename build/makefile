#######################################################
#######################################################
#######################################################
##########                                   ##########
########## Author:  Roman Ulan               ##########
########## Mail:    roman.ulan@gmail.com     ##########
##########                                   ##########
#######################################################
#######################################################
#######################################################

#######################################################
##########        BEGIN User part            ##########
##########       You can change it           ##########
#######################################################
BUILDROOT_PATH=/home/xubuntu/buildroot
HOST_PATH=$(BUILDROOT_PATH)/output/host
CC=$(HOST_PATH)/usr/bin/i686-buildroot-linux-uclibc-gcc
SYSROOT=$(HOST_PATH)/usr/i686-buildroot-linux-uclibc/sysroot

CFLAGS = -Wall -g -I../lib_person
LDFLAGS = -L../lib_person -lperson
SOURCES = ../src/main.c 
NAME = prog
#######################################################
##########        END User part              ##########
#######################################################

#######################################################
##########      BEGIN Automation part        ##########
##########     You shouldn't change it       ##########
#######################################################
OBJECTS = $(SOURCES:.c=.o)

all: $(NAME)

$(NAME): libperson $(OBJECTS)
	$(CC) $(OBJECTS) $(LDFLAGS) -o $(NAME)

%.o: %.c
	$(CC) -c $(CFLAGS) $< -o $@

libperson:
	make -C ../lib_person

clean:
	rm -f $(OBJECTS)
	rm -f $(NAME)
	make -C ../lib_person clean
#######################################################
##########       END Automation part         ##########
#######################################################

