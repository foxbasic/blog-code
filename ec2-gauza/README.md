# ec2-gauza 최신 버전 반영

AWS EC2 접속기인 [ec2-gauza](https://github.com/leejaycoke/ec2-gazua)가 업데이트 되었습니다.  
혹시 처음 들어보신다면 아래 영상을 참고하시면 어떤 툴인지 바로 느낌이 올수있습니다.

![intro](./images/intro.gif)

> 개인적으로 AWS를 사용하시는 분들은 필수로 설치해야할 툴이라고 생각합니다.  

[예전에 기록한 글](https://jojoldu.tistory.com/311)은 최신 버전에서는 설치가 불가능하니, 아래 내용을 따라 재설치 하시면 됩니다.



## 순서

### 1. clone

```bash
git clone https://github.com/leejaycoke/ec2-gazua.git
cd ./ec2-gazua/
pip install --user -r requirements.txt
```

```bash
vim $(which ec2-ssh)
```

![1](./images/1.png)


```bash
vim /etc/waffle/cred.conf
```

![2](./images/2.png)

키 복사

```
vim ~/.ec2-gz
```

```
name: minor

ssh-path: ~/.ssh

credential:
    aws_access_key_id: access-key
    aws_secret_access_key: secret-key
    region: ap-northeast-2

group-tag: Team
name-tag: Name

filter:
    connectable: true

connect-ip:
    default: private

key-file:
    default: auto

user:
    default: ec2-user
```

![3](./images/3.png)

```bash
mkdir ~/.ssh
```

pem키 복사해서 만든다

```bash
vim ~/.bashrc
```

```bash
alias ec2-gz="python /home/사용자계정/ec2-gazua/ec2-gz.py"
```


## 로컬에서 pem키 복사하기 귀찮을때

```bash
cat pem키주소| pbcopy
```

```bash
cat > majorbilling.pem
```