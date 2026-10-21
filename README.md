# 핏로그 (FitLog)

식단, 운동, 체중을 간단하게 기록하는 개인용 안드로이드 앱입니다.
기록은 **내 기기에만** 저장되고 서버로 전송되지 않으며, 계정이나 광고가 없습니다.

> 이 저장소는 설치 파일(APK)만 배포하는 곳입니다. Google Play가 아닌 **직접 배포**입니다.

## 다운로드

- 최신 버전: [Releases 페이지의 latest](https://github.com/HAR00N/fitlog-releases/releases/latest)
- 모든 버전: [Releases](https://github.com/HAR00N/fitlog-releases/releases)

## 설치 방법

1. 안드로이드 기기에서 위 링크로 들어가 `fitlog-vX.Y.Z.apk`를 내려받습니다.
2. 파일을 열면 "알 수 없는 앱 설치" 권한을 요청할 수 있습니다. 사용 중인 브라우저(또는 파일 앱)에 한해 허용합니다.
3. 설치가 끝나면 허용했던 권한은 다시 꺼 두는 것을 권합니다.
4. 처음 실행하면 간단한 안내와 신체정보 입력, 알림 허용 화면이 나옵니다. 신체정보는 건너뛸 수 있습니다.

## 업데이트

- 새 버전 APK를 같은 방법으로 설치하면 **기존 기록을 유지한 채** 업데이트됩니다.
- 업데이트 전에 앱의 `개인 설정 → 전체 데이터 JSON 백업`으로 백업 파일을 만들어 두는 것을 권합니다.
- 설치할 때 "서명이 다르다"는 안내가 나오면 설치하지 말고 이 저장소의 공식 파일인지 확인해 주세요.

## 설치 파일 검증

공식 파일인지 확인하려면 아래 두 가지를 비교합니다.

**1) 파일 체크섬(SHA-256)**: 각 Release에 `SHA256SUMS.txt`가 함께 올라갑니다.

```powershell
# Windows PowerShell
Get-FileHash .\fitlog-vX.Y.Z.apk -Algorithm SHA256
```

```bash
# Linux / macOS
sha256sum -c SHA256SUMS.txt
```

**2) 서명 인증서 지문**: 공식 APK는 항상 아래 인증서로 서명됩니다.

```
SHA-256: BA:0D:14:92:95:08:62:F9:57:AE:65:FE:61:DA:99:35:BB:65:B4:D5:2A:35:18:73:1C:1D:83:DE:36:18:CE:8B
```

```bash
# Android SDK build-tools의 apksigner
apksigner verify --print-certs fitlog-vX.Y.Z.apk
```

출력의 `certificate SHA-256 digest`가 위 값(콜론 제외, 소문자)과 같아야 합니다.

## 알림 권한

타이머 종료를 알리는 데에만 쓰며, 설정에서 언제든 끌 수 있습니다.

## 문의

이 저장소의 Issues를 이용해 주세요.
