# 한글 폴더를 영어로 바꾸기

```bash
export LANG=C
xdg-user-dirs-gtk-update
```

# Git 설치

```bash
sudo apt-get install git
sudo apt-get install git-lfs
```

# WindSurf 설치

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

# Vim 설치

```bash
sudo apt-get install vim
```

# 이모지 설치

```bash
sudo snap install emote
```

# 클립보드 설치

```bash
sudo apt install gnome-shell-extension-gpaste
```

# NeoFetch 설치

```bash
sudo apt-get install neofetch
echo "neofetch" >> ~/.bashrc
```

# 한글 설정

```bash
sudo apt update
sudo apt install -y language-pack-ko fonts-nanum-* fontconfig
sudo fc-cache -f -v
```

# 파이썬 가상환경 없이도 라이브러리 설치할수 있게하기

리눅스에서는 파이썬 라이브러리를 설치할때 가상환경을 설치해야 한다 계속 가상환경을 만들고 라이브러리를 설치하는건 귀찮으니 아래 명령어를 쳐서 해결해보자

```bash
sudo apt-get install python3-pip
python3 -m pip config set global.break-system-packages true
```

# 파이썬 가상환경 쓸수 있게 하기

```bash
sudo apt-get install python3-venv
```

# 가상환경 실행

```bash
python3 -m venv myenv
source myenv/bin/activate
```

# Java 설치

```bash
sudo apt install openjdk-21-jdk
```

# Node.js 설치

```bash
# nvm 다운로드 및 설치:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

# Node.js 다운로드 및 설치:
nvm install 22

# Node.js 버전 확인:
node -v # "v22.18.0"가 출력되어야 합니다.
nvm current # "v22.18.0"가 출력되어야 합니다.

npm 버전 확인:
npm -v # 10.9.3가 출력되어야 합니다.
```

# Docker 설치

```bash
sudo wget -qO- http://get.docker.com/ | sh
```

# Docker 할때 sudo 없이 사용하기

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

# Docker 로그인이 안될 때

```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format long
pass init $your_gpg_id
```

# 이 리포스터지 가져오기

```bash
git clone https://github.com/an0jin/Linux.git
```

# Chrome 설치

```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```


# Discord 설치(비대면 과외할때 필요)

```bash
sudo dpkg -i  discord-0.0.102.deb
```

# GitHub Desktop 설치

```bash
sudo dpkg -i GitHubDesktop-linux-amd64-3.4.13-linux1.deb
```

# ChatGPT Desktop 설치

```bash
sudo snap install chatgpt-desktop-client
```

# Claude Desktop 설치

```bash
sudo dpkg -i claude-desktop_0.12.55_amd64.deb
```
