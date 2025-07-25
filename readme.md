# 한글 폴더를 영어로 바꾸기
```bash
export LANG=C
xdg-user-dirs-gtk-update
```

# Git 설치
```bash
sudo apt-get install git
```

# 이 리포스터지 가져오기
```bash
git clone https://github.com/an0jin/Linux.git
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

# Chrome 설치
```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

# Discord 설치
```bash
sudo dpkg -i discord-0.0.102.deb
```

# GitHub Desktop 설치
```bash
sudo dpkg -i GitHubDesktop-linux-amd64-3.4.13-linux1.deb
```

# 파이썬 가상환경 없이도 라이브러리 설치할수 있게하기
파이썬은 리눅스에서는 가상환경을 설치해야 한다 그방법없이 해보자 
```bash
python3 -m pip config set global.break-system-packages true
sudo apt-get install python3-pip
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