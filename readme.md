# Debian
이 리포스터지를 만든 사람은 snap 때문에 ubuntu계열을 싫어하며 denain을 처음부터 GUI로 해버리면 ibus가 설치되기 때문에 Debian은 CLI로 어느정도 다루고 lxqt를 설치한 후 fcitx5를 설치할 예정이다
## CLI

### sudo 설치
```bash
apt install sudo 
```

#### sudo 권한 주기
```bash
su -
usermod -aG sudo 유저명
```

### 한글 폴더를 영어로 바꾸기
```bash
LANG=C xdg-user-dirs-update --force
```

### Git 설치
```bash
sudo apt-get install git
sudo apt-get install git-lfs
```

### Vim 설치

```bash
sudo apt-get install vim
```

### 파이썬 설치

```bash
sudo apt-get install python3
```

#### 파이썬 pip 설치

```bash
sudo apt-get install python3-pip
```

##### 파이썬 가상환경 쓸수 있게 하기

```bash
sudo apt-get install python3-venv
```

##### 가상환경 실행

```bash
python3 -m venv myenv
source myenv/bin/activate
```
##### 가상환경 안만들고 라이브러리 설치하는법
```bash
python3 -m pip config set global.break-system-packages true
```

### Java 설치

```bash
sudo apt install openjdk-21-jdk
```

### Docker 설치

```bash
sudo apt install docker.io
```

#### Docker 할때 sudo 없이 사용하기

```bash
su - 
usermod -aG docker 유저명
```

### lxqt 설치
```bash
sudo apt-get install lxqt
```
### GUI로 변경하기

```bash
sudo systemctl set-default graphical.target
sudo reboot
```

### NeoFetch 설치

```bash
sudo apt-get install neofetch
echo "neofetch" >> ~/.bashrc
```

## GUI


### 시간 맞추기
```bash
sudo apt update && sudo apt install -y chrony
sudo timedatectl set-ntp true
timedatectl status
```

### 와이파이 설치
```bash
sudo vim /etc/NetworkManager/NetworkManager.conf
```

파일내용을 이렇게 바꾼다 그냥 managed을 true로 바꾸면 된다
```bash
[main]
plugins=ifupdown,keyfile

[ifupdown]
managed=true
```
```bash
sudo vim /etc/network/interfaces
```
파일내용을 이렇게 바꾼다.
```bash
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

auto lo
iface lo inet loopback

```

### fcitx로 변경하기

```bash
sudo apt-get install fcitx5 fcitx5-hangul
```

### 소리 조절 기능 넣기
기본설정->단축키
```bash
pactl set-sink-volume @DEFAULT_SINK@ +5%

```
### 밝기 조절 기능 설치하기
```bash
sudo apt install brightnessctl -y
```
#### 밝기 증가 넣기
기본설정->단축키
```bash
brightnessctl set 5%+
```

#### 밝기 감소 넣기
기본설정->단축키
```bash
brightnessctl set 5%-
```

### 한글 및 이모티콘이 깨질때

```bash
sudo apt install -y fonts-nanum fonts-noto-cjk fonts-noto-color-emoji fonts-symbola
sudo fc-cache -f -v
```

### 리브레 오피스 설치
```bash
sudo apt install --no-install-recommends libreoffice-writer libreoffice-impress libreoffice-calc libreoffice-l10n-ko
```

### tar.gz를 실행프로그램으로 만들어 보자

```bash
sudo tar -zxvf 파일명 -C /opt/
sudo vim "/usr/share/applications/짓고싶은 이름.desktop"
```

#### 파일 내용작성

```bash
[Desktop Entry]
Type=Application(필수)
Name=이름(필수)
Exec="프로그램 위치"(필수)
Icon=아이콘
Categories=주 카테고리;부 카테고리;
```
##### 카테고리 설명

<table>
    <thead>
      <tr>
        <th style="width: 12%;">주 카테고리</th>
        <th style="width: 28%;">주 카테고리 설명</th>
        <th style="width: 60%;">하위 카테고리 및 설명</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="main-cat">AudioVideo</td>
        <td class="main-desc">오디오 및 비디오 재생, 편집, 녹음 관련 애플리케이션 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Database</code> : 미디어 라이브러리 및 데이터베이스 관리</li>
            <li><code>Encoder</code> : 오디오/비디오 인코더 및 변환기</li>
            <li><code>DiscBurning</code> : CD/DVD 굽기 도구</li>
            <li><code>AudioVideoEditing</code> : 오디오/비디오 편집 프로그램</li>
            <li><code>Player</code> : 미디어 플레이어 (재생기)</li>
            <li><code>Recorder</code> : 오디오/비디오 녹화 및 녹음 도구</li>
            <li><code>Audio</code> : 오디오 전용 애플리케이션</li>
            <li><code>Video</code> : 비디오 전용 애플리케이션</li>
            <li><code>Midi</code> : MIDI 관련 소프트웨어</li>
            <li><code>Mixer</code> : 오디오 믹서 및 볼륨 제어</li>
            <li><code>Sequencer</code> : 오디오 시퀀서</li>
            <li><code>Tuner</code> : TV/라디오 튜너</li>
            <li><code>TV</code> : TV 시청 애플리케이션</li>
            <li><code>Music</code> : 음악 재생 및 관리 도구</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Development</td>
        <td class="main-desc">소프트웨어 개발, 프로그래밍, 디버깅 관련 도구 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Building</code> : 빌드 시스템 및 컴파일 도구 (Make, CMake 등)</li>
            <li><code>Debugger</code> : 소프트웨어 디버거</li>
            <li><code>IDE</code> : 통합 개발 환경 (VS Code, IntelliJ 등)</li>
            <li><code>GUIDesigner</code> : GUI 레이아웃 및 UI 디자이너</li>
            <li><code>Profiling</code> : 성능 분석 및 프로파일링 도구</li>
            <li><code>RevisionControl</code> : 버전 관리 시스템 (Git GUI, SVN 등)</li>
            <li><code>Translation</code> : 소프트웨어 번역 및 지역화 도구</li>
            <li><code>WebDevelopment</code> : 웹 개발 관련 도구</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Education</td>
        <td class="main-desc">학습, 교육, 훈련 목적의 소프트웨어 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Art</code> : 미술 교육 도구</li>
            <li><code>Construction</code> : 구조/건축 학습 소프트웨어</li>
            <li><code>Languages</code> : 외국어 학습 소프트웨어</li>
            <li><code>Learning</code> : 일반 학습 도구</li>
            <li><code>MedicalSoftware</code> : 의학 교육 및 참고용 소프트웨어</li>
            <li><code>Music</code> : 음악 교육 및 악기 학습 프로그램</li>
            <li><code>Science</code> : 과학 학습 소프트웨어</li>
            <li><code>Teaching</code> : 교사용 교수 자료 및 수업 도구</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Game</td>
        <td class="main-desc">각종 오락 및 게임 애플리케이션 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>ActionGame</code> : 액션 게임</li>
            <li><code>AdventureGame</code> : 어드벤처 게임</li>
            <li><code>ArcadeGame</code> : 아케이드 게임</li>
            <li><code>BoardGame</code> : 보드 게임</li>
            <li><code>BlocksGame</code> : 블록 및 퍼즐 게임</li>
            <li><code>CardGame</code> : 카드 게임</li>
            <li><code>KidsGame</code> : 어린이용 게임</li>
            <li><code>LogicGame</code> : 두뇌 개발 및 퍼즐 게임</li>
            <li><code>RolePlaying</code> : RPG (롤플레잉 게임)</li>
            <li><code>Shooter</code> : 슈팅 게임</li>
            <li><code>Simulation</code> : 시뮬레이션 게임</li>
            <li><code>SportsGame</code> : 스포츠 게임</li>
            <li><code>StrategyGame</code> : 전략 게임</li>
            <li><code>Emulators</code> : 에뮬레이터 (고전 콘솔 등)</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Graphics</td>
        <td class="main-desc">이미지 생성, 편집, 뷰어 관련 애플리케이션 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>2DGraphics</code> : 2D 그래픽 도구</li>
            <li><code>VectorGraphics</code> : 벡터 그래픽 편집기 (Inkscape 등)</li>
            <li><code>RasterGraphics</code> : 비트맵/래스터 편집기 (GIMP 등)</li>
            <li><code>3DGraphics</code> : 3D 모델링 및 렌더링 (Blender 등)</li>
            <li><code>Scanning</code> : 스캐너 제어 소프트웨어</li>
            <li><code>OCR</code> : 광학 문자 인식 도구</li>
            <li><code>Photography</code> : 사진 관리 및 현상 도구 (Darktable 등)</li>
            <li><code>Publishing</code> : DTP 및 전자 출판 도구</li>
            <li><code>Viewer</code> : 이미지 뷰어</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Network</td>
        <td class="main-desc">인터넷 접속, 통신, 원격 제어 관련 프로그램 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Email</code> : 이메일 클라이언트 (Thunderbird 등)</li>
            <li><code>Dialup</code> : 다이얼업 및 모뎀 연결 도구</li>
            <li><code>InstantMessaging</code> : 메신저 및 채팅 프로그램</li>
            <li><code>IRCClient</code> : IRC 클라이언트</li>
            <li><code>Feed</code> : RSS/Atom 피드 리더</li>
            <li><code>FileTransfer</code> : FTP 및 파일 전송 클라이언트 (FileZilla 등)</li>
            <li><code>HamRadio</code> : 아마추어 무선 관련 프로그램</li>
            <li><code>News</code> : 뉴스그룹 리더</li>
            <li><code>P2P</code> : P2P 및 토렌트 클라이언트</li>
            <li><code>RemoteAccess</code> : 원격 데스크톱 및 SSH 접속 도구</li>
            <li><code>Telephony</code> : VoIP 및 전화 통화 프로그램</li>
            <li><code>WebBrowser</code> : 웹 브라우저 (Firefox, Chrome 등)</li>
            <li><code>WebDevelopment</code> : 웹 사이트 제작 및 관리 도구</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Office</td>
        <td class="main-desc">사무 처리, 문서 작성, 일정 관리 관련 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Calendar</code> : 달력 및 일정 관리 도구</li>
            <li><code>ContactManagement</code> : 주소록 및 연락처 관리</li>
            <li><code>Database</code> : 사무용 데이터베이스 관리</li>
            <li><code>Dictionary</code> : 사전 프로그램</li>
            <li><code>Chart</code> : 차트 및 그래프 생성 도구</li>
            <li><code>Email</code> : 오피스용 이메일 클라이언트</li>
            <li><code>Finance</code> : 개인 자산 및 회계 관리 프로그램</li>
            <li><code>FlowChart</code> : 순서도 작성 도구</li>
            <li><code>PDFAViewer</code> : PDF 및 문서 뷰어</li>
            <li><code>Presentation</code> : 프레젠테이션 프로그램 (Impress 등)</li>
            <li><code>ProjectManagement</code> : 프로젝트 일정 관리 도구</li>
            <li><code>Publishing</code> : 전자 출판 및 DTP</li>
            <li><code>Spreadsheet</code> : 스프레드시트 (Calc, Excel 등)</li>
            <li><code>WordProcessor</code> : 워드 프로세서 (Writer, Word 등)</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Science</td>
        <td class="main-desc">수학, 과학, 공학 연구용 전문 프로그램 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>ArtificalIntelligence</code> : 인공지능 및 머신러닝 연구 도구</li>
            <li><code>Astronomy</code> : 천문학 및 성도 프로그램</li>
            <li><code>Biology</code> : 생물학 분석 소프트웨어</li>
            <li><code>Chemistry</code> : 화학식 및 분자 구조 분석 도구</li>
            <li><code>ComputerScience</code> : 컴퓨터 공학 연구 도구</li>
            <li><code>DataVisualization</code> : 데이터 시각화 도구</li>
            <li><code>Economy</code> : 경제학 및 통계 모델링 도구</li>
            <li><code>Electricity</code> : 전기/전자 회로 설계 및 시뮬레이션</li>
            <li><code>Geography</code> : 지리학 및 GIS 도구</li>
            <li><code>Geology</code> : 지질학 관련 프로그램</li>
            <li><code>Geoscience</code> : 지구과학 일반 도구</li>
            <li><code>History</code> : 역사 연구 및 사료 관리 도구</li>
            <li><code>ImageProcessing</code> : 과학용 학술 이미지 처리 도구</li>
            <li><code>Math</code> : 수학 연산 및 수식 처리 소프트웨어</li>
            <li><code>MedicalSoftware</code> : 의학 정보 및 진단 보조 프로그램</li>
            <li><code>NumericalAnalysis</code> : 수치 해석 프로그램 (MATLAB, Octave 등)</li>
            <li><code>ParallelComputing</code> : 병렬 연산 관련 소프트웨어</li>
            <li><code>Physics</code> : 물리학 시뮬레이션 도구</li>
            <li><code>Robotics</code> : 로봇 공학 및 제어 소프트웨어</li>
            <li><code>Sports</code> : 스포츠 과학 분석 도구</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Settings</td>
        <td class="main-desc">데스크톱 환경 및 시스템 환경설정 관련 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>DesktopSettings</code> : 데스크톱 테마 및 외관 설정</li>
            <li><code>HardwareSettings</code> : 드라이버, 하드웨어 장치 설정</li>
            <li><code>PackageManager</code> : 패키지 관리자 및 업데이트 설정</li>
            <li><code>Security</code> : 보안 및 방화벽 설정</li>
            <li><code>Accessibility</code> : 접근성 설정 (돋보기, 화면 낭독기 등)</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">System</td>
        <td class="main-desc">운영체제 관리, 시스템 모니터링, 파일 관리 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Emulator</code> : 터미널 에뮬레이터 또는 OS 에뮬레이터</li>
            <li><code>FileManager</code> : 파일 관리자 (Nautilus, Dolphin 등)</li>
            <li><code>TerminalEmulator</code> : 터미널 실행 프로그램</li>
            <li><code>Filesystem</code> : 디스크 파티션 및 파일시스템 도구</li>
            <li><code>Monitor</code> : 시스템 자원 모니터</li>
            <li><code>Security</code> : 시스템 백신 및 보안 유틸리티</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td class="main-cat">Utility</td>
        <td class="main-desc">일반적인 보조 도구 및 액세서리 프로그램 카테고리</td>
        <td>
          <ul class="sub-list">
            <li><code>Archiving</code> : 압축 및 압축 해제 프로그램</li>
            <li><code>Calculator</code> : 계산기</li>
            <li><code>Clock</code> : 시계, 알람, 타이머</li>
            <li><code>Compression</code> : 데이터 압축 전용 도구</li>
            <li><code>FileTools</code> : 파일 검색, 이름 변경 등의 전용 도구</li>
            <li><code>Maps</code> : 지도 및 GPS 유틸리티</li>
            <li><code>Spirituality</code> : 종교 및 명상 관련 앱</li>
            <li><code>TextEditor</code> : 일반 텍스트 편집기 (Gedit, Kate 등)</li>
          </ul>
        </td>
      </tr>
    </tbody>
  </table>

### CLI로 변경하기

```bash
sudo systemctl set-default multi-user.target
sudo reboot
```

# Oracle Linux
이 리포스터지를 만든사람의 오라클 리눅스는 단순 OCI에서 받은 클라우드 VM으로 쓰기때문에 도커만 설치할 예정이다

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
curl -fsSL https://get.docker.com | sudo sh
```

### Docker 할때 sudo 없이 사용하기

```bash
sudo usermod -aG docker $USER
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
