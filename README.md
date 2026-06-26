# Kakao Skills

카카오톡 데스크톱 앱을 Codex, Claude Code 같은 AI 코딩/자동화 환경에서 다루기 위한 스킬 모음입니다.

## 포함된 스킬

- `kakao-chat`: macOS 또는 Windows의 카카오톡 데스크톱 UI를 이용해 특정 대화를 읽거나, 사용자가 확인한 메시지를 전송하는 스킬입니다.

이 스킬은 카카오톡 공식 API를 사용하지 않습니다. 실행 환경에 따라 macOS 접근성 자동화, Windows Codex Computer Use, Windows PowerShell fallback 경로를 안내합니다.

## 설치 방법

가장 쉬운 방법은 Codex나 Claude Code 같은 AI에게 이 저장소 주소를 알려주고 설치를 요청하는 것입니다.

예시:

```text
https://github.com/volition79/kakao-skills 에 있는 kakao-chat 스킬을 설치해줘.
```

또는:

```text
이 GitHub 저장소를 Codex/Claude Code 스킬로 설치해줘:
https://github.com/volition79/kakao-skills
```

AI가 스킬 설치 기능을 지원한다면 저장소를 내려받아 적절한 스킬 폴더에 설치합니다.

## 설치 후 해야 할 일

스킬 설치가 끝나면 터미널 또는 Codex/Claude Code 세션을 다시 실행하세요.

이미 실행 중인 세션은 새로 설치된 스킬을 바로 인식하지 못할 수 있습니다. 재실행 후 `$kakao-chat` 또는 자연어 요청으로 사용할 수 있습니다.

예시:

```text
$kakao-chat으로 카카오톡에서 홍길동과의 대화를 읽어줘.
```

```text
카카오톡에서 홍길동에게 "안녕하세요"라고 보내줘. 보내기 전에 확인해줘.
```

## 사용 전 권한 안내

- macOS에서는 카카오톡과 Codex/Claude Code가 실행되는 터미널 또는 앱에 손쉬운 사용 권한이 필요할 수 있습니다.
- Windows + Codex에서는 Codex 앱이 실행 중이고 Computer Use가 승인되어 있으면 가장 안정적으로 동작합니다.
- Windows에서 Computer Use를 사용할 수 없으면 스킬은 PowerShell/Win32 기반 fallback 절차를 안내합니다.

## 안전 원칙

- 메시지를 전송하기 전에는 받는 사람과 메시지 본문을 사용자에게 확인해야 합니다.
- 로그인, 보안 인증, 휴대폰 인증이 필요한 경우 사용자가 직접 처리해야 합니다.
- 읽을 수 없는 이미지, 파일, 삭제 메시지의 내용은 추측하지 않습니다.
