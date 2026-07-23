# Lubuntu

## 한글 폴더를 영어로 바꾸기

```bash
export LANG=C
xdg-user-dirs-gtk-update
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

## 이 리포스터지 가져오기

```bash
git clone https://github.com/an0jin/Linux.git
```

## Chrome 설치

```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## 아래아 한글 설치
한글은 리눅스를 지원하지 않으니 [해당 리포스터지](https://github.com/golbin/hop)를 참고해서 프로그램을 다운받자

```bash
sudo dpkg -i HOP-linux-x64.deb
```



## gemini cli설치

```bash
npm install -g @google/gemini-cli
```


## Antigravity IDE를 실행프로그램으로 만들어 보자

```bash
sudo tar -zxvf AntigravityIDE.tar.gz -C /opt/
sudo vim "/usr/share/applications/Antigravity IDE.desktop"
```

### 파일 내용작성

```bash
[Desktop Entry]
Version=1.0
Type=Application
Name=Antigravity IDE
Comment=Antigravity IDE 개발 도구
Exec=/opt/AntigravityIDE/antigravity-ide
Icon=/opt/AntigravityIDE/resources/app/resources/linux/code.png
Terminal=false
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
Version=1.0
Type=Application
Name=Antigravity 2.0
Comment=Antigravity 2.0임
Exec=/opt/Antigravity-x64/antigravity --no-sandbox
Icon=/opt/AntigravityIDE/resources/app/resources/linux/code.png
Terminal=false
Categories=Development;IDE;
```

## Antigravity cli설치

```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

## GitHub Desktop 설치

리눅스 계열은 Github Desktop을 지원을 안하기 때문에 [해당 리포스터지](https://github.com/desktop-plus/desktop-plus)를 이용하면 된다

```bash
sudo curl https://gpg.desktop-plus.org/public.key | sudo gpg --dearmor -o /usr/share/keyrings/desktop-plus.gpg
echo "deb [arch=amd64,arm64 signed-by=/usr/share/keyrings/desktop-plus.gpg] https://apt.desktop-plus.org/ stable main" | sudo tee /etc/apt/sources.list.d/desktop-plus.list
sudo apt update
sudo apt install desktop-plus
```
## Discord 설치(비대면 과외할때 필요)

```bash
sudo dpkg -i  discord-0.0.102.deb
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
