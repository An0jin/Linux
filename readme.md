# Lubuntu

## 한글 폴더를 영어로 바꾸기

```bash
LANG=C xdg-user-dirs-update --force
```

## CLI로 변경하기

```bash
sudo systemctl set-default multi-user.target
sudo reboot
```

## GUI로 변경하기

```bash
sudo systemctl set-default graphical.target
sudo reboot
```

## Git 설치

```bash
sudo apt-get install git
sudo apt-get install git-lfs
```

## Vim 설치

```bash
sudo apt-get install vim
```

## 이모지 설치

```bash
sudo snap install emote
```

## NeoFetch 설치

```bash
sudo apt-get install neofetch
echo "neofetch" >> ~/.bashrc
```

## 한글 설정

```bash
sudo apt update
sudo apt install -y language-pack-ko fonts-nanum-* fontconfig
sudo fc-cache -f -v
```

## 파이썬 가상환경 없이도 라이브러리 설치할수 있게하기

리눅스에서는 파이썬 라이브러리를 설치할때 가상환경을 설치해야 한다 계속 가상환경을 만들고 라이브러리를 설치하는건 귀찮으니 아래 명령어를 쳐서 해결해보자

```bash
sudo apt-get install python3-pip
python3 -m pip config set global.break-system-packages true
```

### 파이썬 가상환경 쓸수 있게 하기

```bash
sudo apt-get install python3-venv
```

### 가상환경 실행

```bash
python3 -m venv myenv
source myenv/bin/activate
```

## Java 설치

```bash
sudo apt install openjdk-21-jdk
```
## Docker 설치

```bash
sudo wget -qO- http://get.docker.com/ | sh
```

### Docker 할때 sudo 없이 사용하기

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

### Docker 로그인이 안될 때

```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format long
pass init $your_gpg_id
```

## Antigravity IDE를 실행프로그램으로 만들어 보자

```bash
sudo tar -zxvf Antigravity IDE.tar.gz -C /opt/
sudo vim "/usr/share/applications/Antigravity IDE.desktop"
```

### 파일 내용작성

```bash
[Desktop Entry]
Type=Application
Name=Antigravity IDE
Exec="/opt/Antigravity IDE/antigravity-ide"
Icon="/opt/Antigravity IDE/resources/app/resources/linux/code.png"
Categories=Development;IDE;
```

## Antigravity 2.0을 실행프로그램으로 만들어 보자

```bash
sudo tar -zxvf Antigravity.tar.gz -C /opt/
sudo vim "/usr/share/applications/Antigravity.desktop"
```

### 파일 내용작성

```bash
[Desktop Entry]
Type=Application
Name=Antigravity 2.0
Exec=/opt/Antigravity-x64/antigravity --no-sandbox
Icon=/opt/AntigravityIDE/resources/app/resources/linux/code.png
Categories=Development;IDE;
```

# Oracle Linux(OCI)

## 해당 클라우드에 접속하기

```bash
chmod 400 [개인키]
ssh -i [개인키] opc@[ip]
```

## Docker 설치

```bash
sudo dnf update -y
sudo dnf install -y dnf-utils
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Docker 설치

```bash
sudo dnf update -y
sudo dnf install -y dnf-utils
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Docker 할때 sudo 없이 사용하기

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

## 용량부족 해결볍

```bash
sudo fallocate -l 2G /swapfile2  ## 2GB 스왑 파일 생성
sudo chmod 600 /swapfile2      ## 권한 설정
sudo mkswap /swapfile2         ## 스왑 포맷
sudo swapon /swapfile2         ## 스왑 활성화
echo '/swapfile2 none swap sw 0 0' | sudo tee -a /etc/fstab
sudo sysctl vm.swappiness=10
```

## 포트 문제가 생긴다면

```bash
sudo firewall-cmd --zone=public --add-port=8000/tcp --permanent
sudo firewall-cmd --zone=public --add-port=5432/tcp --permanent
sudo firewall-cmd --zone=public --add-port=22/tcp --permanent
sudo firewall-cmd --reload
```
