// git 2.45.0 설치

//curl: wget이랑 비슷하지만, wget보다 업그레이드
1. 의존성 설치
# yum -y install curl-devel
# yum -y install expat-devel
# yum -y install gettext-devel
# yum -y install openssl-devel
# yum -y install zlib-devel
# yum -y install perl-devel

2. git 다운로드
# wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.45.0.tar.gz

3. 압축 풀기
# tar xvfz git-2.45.0.tar.gz

4. 소스 디렉토리 이동
# cd git-2.45.0

5. configure build environment
[root@localhost git-2.45.0]# ./configure --prefix=/usr/local/poscodx/git-2.45.0 

6. 빌드
[root@localhost git-2.45.0]# make all
[root@localhost git-2.45.0]# make

7. 설치
[root@localhost git-2.45.0]# make install 
[root@localhost git-2.45.0]# cd //설치하고 나오기  

8. 링크 생성(모두 절대경로로 지정)
[root@localhost ~]# cd /usr/local/poscodx
[root@localhost ~]# ln -s git-2.45.0/ git
[root@localhost ~]# ls -l //링크 연결 체크 

*링크 걸어놓은 거 잘못했을 때 삭제 
링크 걸어놓은 경로로 들어간 뒤 
rm -f git

9. 설정(vi /etc/profile)
//제일 마지막줄에 insert 모드로 입력
# git 
export PATH=$PATH:/usr/local/poscodx/git/bin

10. 확인
# source /etc/profile
# git --version
