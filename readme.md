
# 공통(Ubuntu Desktop or oracle linux)

## 한글 폴더를 영어로 바꾸기

```bash
export LANG=C
xdg-user-dirs-gtk-update
```
# ubuntu
## Git 설치

```bash
sudo apt-get install git
sudo apt-get install git-lfs
```

## WindSurf 설치

```bash
sudo apt-get install wget gpg
wget -qO- "https://windsurf-stable.codeiumdata.com/wVxQEIWkwPUEAGf3/windsurf.gpg" | gpg --dearmor > windsurf-stable.gpg
sudo install -D -o root -g root -m 644 windsurf-stable.gpg /etc/apt/keyrings/windsurf-stable.gpg
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/windsurf-stable.gpg] https://windsurf-stable.codeiumdata.com/wVxQEIWkwPUEAGf3/apt stable main" | sudo tee /etc/apt/sources.list.d/windsurf.list > /dev/null
rm -f windsurf-stable.gpg
sudo apt install apt-transport-https
sudo apt update
sudo apt install windsurf
```

## Vim 설치

```bash
sudo apt-get install vim
```

## 이모지 설치

```bash
sudo snap install emote
```

## 클립보드 설치

```bash
sudo apt install gnome-shell-extension-gpaste
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

## 파이썬 가상환경 쓸수 있게 하기

```bash
sudo apt-get install python3-venv
```

## 가상환경 실행

```bash
python3 -m venv myenv
source myenv/bin/activate
```

## Java 설치

```bash
sudo apt install openjdk-21-jdk
```

## Node.js 설치

```bash
## nvm 다운로드 및 설치:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

## Node.js 다운로드 및 설치:
nvm install 22

## Node.js 버전 확인:
node -v ## "v22.18.0"가 출력되어야 합니다.
nvm current ## "v22.18.0"가 출력되어야 합니다.

npm 버전 확인:
npm -v ## 10.9.3가 출력되어야 합니다.
```

## Docker 설치

```bash
sudo wget -qO- http://get.docker.com/ | sh
```

## Docker 할때 sudo 없이 사용하기

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

## Docker 로그인이 안될 때

```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format long
pass init $your_gpg_id
```

## 이 리포스터지 가져오기

```bash
git clone https://github.com/an0jin/Linux.git
```

## Chrome 설치

```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```


## Discord 설치(비대면 과외할때 필요)

```bash
sudo dpkg -i  discord-0.0.102.deb
```

## GitHub Desktop 설치

```bash
sudo dpkg -i GitHubDesktop-linux-amd64-3.4.13-linux1.deb
```



# Oracle Linux

## wifi 인식이 안 될떄 대처법
```bash
sudo dnf install iwl7260-firmware linux-firmware
sudo modprobe -r iwlwifi
sudo modprobe iwlwifi
nmcli device status
```

## Git 설치

```bash
sudo dnf install git
sudo dnf install git-lfs
```

## WindSurf 설치

```bash
sudo rpm --import https://windsurf-stable.codeiumdata.com/wVxQEIWkwPUEAGf3/yum/RPM-GPG-KEY-windsurf
echo -e "[windsurf]
name=Windsurf Repository
baseurl=https://windsurf-stable.codeiumdata.com/wVxQEIWkwPUEAGf3/yum/repo/
enabled=1
autorefresh=1
gpgcheck=1
gpgkey=https://windsurf-stable.codeiumdata.com/wVxQEIWkwPUEAGf3/yum/RPM-GPG-KEY-windsurf" | sudo tee /etc/yum.repos.d/windsurf.repo > /dev/null
sudo dnf check-update
sudo dnf install -y windsurf
```

## pip설치 및 가상환경 없이도 라이브러리 설치할수 있게하기

리눅스에서는 파이썬 라이브러리를 설치할때 가상환경을 설치해야 한다 계속 가상환경을 만들고 라이브러리를 설치하는건 귀찮으니 아래 명령어를 쳐서 해결해보자

```bash
sudo dnf install python3-pip
python3 -m pip config set global.break-system-packages true
```

## 파이썬 가상환경 쓸수 있게 하기

```bash
sudo dnf install python3-venv
```

## 가상환경 실행

```bash
python3 -m venv myenv
source myenv/bin/activate
```

## Node.js 설치

```bash
## nvm 다운로드 및 설치:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

## Node.js 다운로드 및 설치:
nvm install 22

## Node.js 버전 확인:
node -v ## "v22.21.0"가 출력되어야 합니다.
nvm current ## "v22.21.0"가 출력되어야 합니다.

## Verify the Node.js version:
node -v ## Should print "v22.21.0".

#npm 버전 확인:
npm -v ## 10.9.4가 출력되어야 합니다.

```



## docker 설치
```bash
sudo dnf update -y	
sudo dnf install -y dnf-utils
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Docker 할때 sudo 없이 사용하기

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

## 이 리포스터지 가져오기

```bash
git clone https://github.com/an0jin/Linux.git
```

## Chrome 설치

```bash
sudo dnf install google-chrome-stable_current_x86_64.rpm
```


## Discord 설치(비대면 과외할때 필요)

```bash
tar -zxvf  desktop-release-3.4.13-linux1.tar.gz
```

## GitHub Desktop 설치

```bash
sudo dnf install GitHubDesktop-linux-x86_64-3.4.12-linux1.rpm
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

# oracle cloud에서 사용할떄

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
