# Practice_3

https://github.com/ustoopia/Live-stream-server-portable-Windows-Nginx-RTMP-HLS-Dash

C:/livestream/ 폴더를 생성 후 그 안에 압축 해제
![image](https://github.com/user-attachments/assets/e463e501-f3bb-40f0-9cf9-017ac3d81ae4)

LOSC가 업로드한 360도 축구 영상
https://www.dropbox.com/s/l85xv6ecp1i993c/1-8-Football.mp4?dl=0

FFMPEG 파일 다운로드
https://www.gyan.dev/ffmpeg/builds

사용 코드
ffmpeg -re -i “1-8-Football.mp4" –c:v libx264 –c:a aac –ar 44100 –ac 1 –f flv rtmp://localhost/live/stream

ffmpeg -re -i 1-8-Football.mp4 -filter_complex "[0:v]crop=iw/3:ih/2:trunc(1*iw/3):trunc(1*ih/2)[selected_tile]" -map "[selected_tile]" -c:v libx264 -preset veryfast -b:v 3000k -maxrate 3500k -bufsize 6000k -c:a aac -ar 44100 -ac 1 -f flv rtmp://localhost/live/stream

