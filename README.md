# Os-pr-1
#include<stdio.h>
#include<sys/stat.h>
#include<sys/types.h>
#include<fcntl.h>
#include<unistd.h>


int main()
{
	int fd,retval;
	char buffer[8]="TESTDATA";
	fflush(stdin);
	retval=mkfifo("/home/student/text",0666);
	fd=open("/home/student/text",O_WRONLY);
	write(fd,buffer,sizeof(buffer));
	close(fd);
 return(0);
}
FIFO_READ
#include<stdio.h>
#include<sys/stat.h>
#include<sys/types.h>
#include<unistd.h>
#include<fcntl.h>

int main()
{
	int fd,retval;
	char buffer[8];
	fd=open("/home/student/text",O_RDONLY);
	retval=read(fd,buffer,sizeof(buffer));
	fflush(stdin);	
	write(1,buffer,sizeof(buffer));
	close(fd);
 return(0);
}
