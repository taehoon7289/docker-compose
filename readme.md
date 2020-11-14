##docker-compose 설치 및 사용방법
- centOS 기준이며 yum 으로 패키지 설치 과정
- yum 사용시 root권한이 필요하므로 $ sudo -s 으로 root권한으로 진행 
1. git 설치
<pre>
  <code>
    $ yum update
    $ git install -y git
  </code>
</pre>

<pre>
  <code>
    $ yum install docker-ce-18.06.3.ce-3.el7
    $ curl -L https://github.com/docker/compose/releases/download/1.25.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
    $ chmod 755 /usr/local/bin/docker-compose
  </code>
</pre>

2. /home 디렉토리로 이동
<pre>
  <code>
    $ cd /home
  </code>
</pre>

3. 현재 github clone
<pre>
  <code>
    $ git clone https://github.com/taehoon7289/docker-compose.git
  </code>
</pre>

4. /home 에서 docker-compose 디렉토리 생성되며, docker-compose 로 이동
<pre>
  <code>
    $ cd /home/docker-compose
  </code>
</pre>

5. .env 파일에 각 환경에 맞는 변수값 지정
<pre>
  <code>
    $ vi /home/docker-compose/.env
  </code>
</pre>

6. docker-compose.yml 변경할 값이 있는경우 변경
<pre>
  <code>
    $ vi /home/docker-compose/docker-compose.yml
  </code>
</pre>

7. httpd 의 conf 값 설정 및 Dockerfile EXPOSE 값 변경
- apache2 디렉토리 내부의 conf값 설정시 포트를 변경되었을 경우
Dockerfile 의 EXPOSE 값도 함께 변경해줘야함.
<pre>
  <code>
    $ cd /home/docker-compose/build/httpd/apache2 // httpd 디렉토리 
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/vhosts.conf // 가상호스트 설정
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/ssl.conf // ssl 가상호스트 설정
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/listen.conf // 포트 설정
  </code>
</pre>

8. 시작/종료/재시작 (/home/docker-compose 위치에서 아래 명령어 실행해야함.) 
<pre>
  <code>
    $ cd /home/docker-compose
    $ docker-compose up -d --build
    $ docker-compose kill
    $ docker-compose restart // Dockerfile변경 없는경우
  </code>
</pre>
