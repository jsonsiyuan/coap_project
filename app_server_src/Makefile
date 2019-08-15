



MY_INCLUDES =  -I ../include/coap2/  
export MY_DEFIEN +=  -D HAVE_ASSERT_H -D HAVE_ARPA_INET_H -D HAVE_NETINET_IN_H -D HAVE_SYS_SOCKET_H  -D HAVE_LIMITS_H -D HAVE_MALLOC
MY_DEFIEN +=  -D HAVE_STDIO_H -D HAVE_STRNLEN -D HAVE_TIME_H -D HAVE_SYS_TIME_H -D HAVE_SYS_SELECT_H -D HAVE_SYS_IOCTL_H -D HAVE_SYS_UIO_H -D HAVE_UNISTD_H -D HAVE_SYS_TIME_H
export MY_CFLAGS +=   ${MY_INCLUDES}  ${MY_DEFIEN} -lm -g 

APP_NAME=app_server


#=================================================================================
#								Main entrance
#=================================================================================
all: $(APP_NAME)


APP_FILE=*.c  ../src/*.c  

APP_OBJECTS = $(patsubst %.c,%.o,$(wildcard $(APP_FILE) ))

$(APP_OBJECTS) : %.o:%.c
	gcc -c $(MY_CFLAGS) $(MY_INCLUDES) $(DEFS) $< -o $@ 


$(APP_NAME): $(APP_OBJECTS) 
	gcc -o $(APP_NAME)  $(MY_CFLAGS) $(APP_OBJECTS) $(MY_LIBS)

clean:
	rm -f ./*.o app_server
	rm -f ../src/*.o
.PHONY: clean

