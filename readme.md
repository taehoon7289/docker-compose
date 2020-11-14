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
    $ git install -y docker-ce
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

