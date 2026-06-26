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

## 수동 설치 예시

AI가 자동 설치를 지원하지 않거나 직접 설치하고 싶다면 `kakao-chat` 폴더를 사용하는 도구의 skills 폴더에 복사하면 됩니다.

### Codex 전역 설치

macOS/Linux:

```bash
git clone https://github.com/volition79/kakao-skills.git
mkdir -p ~/.codex/skills
cp -R kakao-skills/kakao-chat ~/.codex/skills/kakao-chat
```

Windows PowerShell:

```powershell
git clone https://github.com/volition79/kakao-skills.git
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.codex\skills" | Out-Null
Copy-Item -Recurse -Force .\kakao-skills\kakao-chat "$env:USERPROFILE\.codex\skills\kakao-chat"
```

### 프로젝트별 설치

특정 프로젝트에서만 쓰고 싶다면 프로젝트 루트의 `.codex/skills` 아래에 복사합니다.

```text
your-project/
  .codex/
    skills/
      kakao-chat/
        SKILL.md
        agents/
          openai.yaml
```

Claude Code 등 다른 도구에서는 해당 도구가 지원하는 사용자/프로젝트 skills 폴더에 `kakao-chat` 디렉터리를 그대로 복사하세요.

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

- 카카오톡 데스크톱 앱이 설치되어 있고 로그인되어 있어야 합니다.
- macOS에서는 카카오톡과 Codex/Claude Code가 실행되는 터미널 또는 앱에 손쉬운 사용 권한이 필요할 수 있습니다.
- Windows + Codex에서는 Codex 앱이 실행 중이고 Computer Use가 승인되어 있으면 가장 안정적으로 동작합니다.
- Windows에서 Computer Use를 사용할 수 없으면 스킬은 PowerShell/Win32 기반 fallback 절차를 안내합니다.

## 설치 확인

재실행 후 AI에게 다음처럼 물어보세요.

```text
현재 설치된 스킬 중 kakao-chat이 있는지 확인해줘.
```

또는 바로 사용 요청을 할 수 있습니다.

```text
$kakao-chat을 사용해서 카카오톡에서 홍길동 대화를 읽어봐.
```

## 안전 원칙

- 메시지를 전송하기 전에는 받는 사람과 메시지 본문을 사용자에게 확인해야 합니다.
- 로그인, 보안 인증, 휴대폰 인증이 필요한 경우 사용자가 직접 처리해야 합니다.
- 읽을 수 없는 이미지, 파일, 삭제 메시지의 내용은 추측하지 않습니다.
