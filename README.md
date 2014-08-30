
#include <sys/wait.h>
#include <sys/socket.h>

 
#include <linux/input.h>  
#include <fcntl.h>  
#include <sys/time.h>   
#include <sys/stat.h>  
#include <unistd.h> 

#define PORT 5000
#define BACKLOG 10
#define LENGTH 512

int main(void)
int main(int argc,char **argv)
{
 int sockfd,nsockfd;
 int num;
 int sin_size;
 
 int fd, retval;  
 char buf[6];  
 fd_set readfds;  
 struct timeval tv;  
 fd = open( "/dev/input/mice", O_RDONLY );   
    
 char sdbuf[LENGTH];
 struct sockaddr_in addr_local;
 struct sockaddr_in addr_remote;
 char sendstr[16]={"123456789abcde"};
 
 if(fd<0) {  
           printf("Failed to open \"/dev/input/mice\".\n");  
           exit(1);  
       } 
else {  
           printf("open \"/dev/input/mice\" successfuly.\n");  
     }   

 if((sockfd=socket(AF_INET,SOCK_STREAM,0))==-1)
 {
 int main(void)
 if(!fork())
 {
  printf("Mr Jiajia You can enter string,and press 'exit' to end the connect.\n");
 while(strcmp(sdbuf,"exit")!=0)
  {
  scanf("%s",sdbuf);
  if(num=send(nsockfd,sdbuf,strlen(sdbuf),0)==-1)
   {
  printf("ERROR:Failed to send string.\n");
  close(sockfd);
  exit(1);
   }


 printf("Mr Yangjiajia:Send %d bytes successfully,please enter gain!\n",num);
  }

  
  while(1) 
{  
         tv.tv_sec = 5;  
         tv.tv_usec = 0;  
         FD_ZERO( &readfds );  
         FD_SET( fd, &readfds );  
         retval = select( fd+1, &readfds, NULL, NULL, &tv );  
         if(retval==0) {  
         printf( "Time out!\n" );  
       }  
          if(FD_ISSET(fd,&readfds)) {   
             if(read(fd, buf, 6) <= 0) {  
                continue;  
            }  
             
  printf("Button type = %d, X = %d, Y = %d, Z = %d\n", (buf[0] & 0x07), buf[1], buf[2],   buf[3]);  
          }  
    }  
     close(fd);  
 }
 close (nsockfd);
 while(waitpid(-1,NULL,WNOHANG)>0);
