1. install docker  Toolbox

2. Download docker file,letakan pada direktori tertentu.
    contoh : C:\User\Student\responsi
	
3. Jalankan  Docker QuickStart Terminal

4. Masuk kedalam direktori tempat mendownload: C:\User\Student\responsi

5. Isi dalam docker File tersebut diganti menjadi: 
    FROM alpine:latest
	MAINTAINER Bambang Purnomosidi <bdfl@bpdp.xyz>
	LABEL version="1.0"
	LABEL description="Run fortune - random citation" 

	RUN ["/bin/rm", "/etc/apk/repositories"]
	RUN echo "http://dl-3.alpinelinux.org/alpine/edge/main" > /etc/apk/repositories
	RUN echo "http://dl-3.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories

	RUN ["/sbin/apk", "update"]
	RUN ["/sbin/apk", "add", "fortune"]

	CMD ["/usr/bin/fortune"]

6. Buka kembali docker quickStart terminal untuk membuka direktori tersebut :
   cd responsi
 
7. membuat Image:
    a. build image :
       docker build -t fikri/dcf . 

 8. Jalankan dengan ;
     docker run -it fikri/dcf 