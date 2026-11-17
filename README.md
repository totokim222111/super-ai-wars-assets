# 슈퍼 AI 대전 어셋

[슈퍼 AI 대전](https://github.com/totokim222111/super-ai-wars)에서 사용하는 그림·음악·효과음·시네마틱 영상입니다.

2026-11-17 소스 공개본입니다. [소스 ZIP](https://github.com/totokim222111/super-ai-wars/releases/download/v2026.11.17/super-ai-wars-assets-2026-11-17.zip)과 [일반판·타입 O 미남판 실행 ZIP](https://github.com/totokim222111/super-ai-wars/releases/tag/v2026.11.17)을 받을 수 있습니다.

## 게임을 실행하려면

아래 요청문을 AI 도우미에게 그대로 붙여넣어 주세요. 게임과 엔진, 이 어셋을 함께 설치하는 요청문입니다.

```text
내 컴퓨터에서 슈퍼 AI 대전을 플레이할 수 있게 설치하고 실행해줘.
직접 명령을 실행할 수 있으면 진행해주고, 채팅만 가능하면 내 운영체제를 물어본 뒤 내가 따라 할 명령을 차례로 알려줘.

1. 기존 파일을 덮어쓰지 않는 새 작업 폴더를 정해줘. Git, Node.js 24 이상, Python 3.11 이상을 확인하고, 없는 것은 설치를 도와줘. Python 그림 검사에 필요한 Pillow와 NumPy도 확인해줘.
2. 아래 세 저장소를 받아줘.
   게임: https://github.com/totokim222111/super-ai-wars
   엔진: https://github.com/totokim222111/super-ai-wars-engine
   어셋: https://github.com/totokim222111/super-ai-wars-assets
3. 게임은 super-ai-wars/에, 엔진은 그 안의 super-ai-wars/engine/에 받아줘. 어셋은 게임 옆의 super-ai-wars-assets/에 받아줘.
4. 엔진 폴더에서 npm ci를 실행해줘.
5. 어셋 저장소의 pack/ 내용만 게임의 pack/에 합쳐줘. README나 .git 폴더는 복사하지 말아줘. 겹치는 pack/audio/pack.json은 두 파일이 같은지 확인해줘.
6. 게임 폴더에서 npm run check와 npm run build를 실행해줘. 공개 저장소에 없는 작업실 원고가 필요한 전체 샘플 테스트 대신 이 두 명령으로 확인해줘. 오류가 나면 실제 로그를 읽고 원인을 해결해줘.
7. 게임 폴더에서 npm run dev로 서버를 켜고, 출력된 주소의 /game.html을 열어줘. 서버가 켜져 있는지 확인하고 접속 주소와 종료 방법을 알려줘.
```

직접 설치하려면 [게임 저장소의 설치 절차](https://github.com/totokim222111/super-ai-wars#실행하기)를 따르세요. 이 저장소의 `pack/` 내용만 게임 폴더의 `pack/`에 합칩니다.

## PLEASE

PLEASE는 "제발 한 번 봐주세요" 하는 장난입니다. 관심 가져주시는 것만으로도 감사합니다.

제가 만든 부분은 마음껏 쓰고, 고치고, 나누고, 판매하셔도 됩니다. 출처 표시도 의무는 아닙니다. 자세한 내용은 [LICENSE](LICENSE)에 적었습니다.

다른 분들이 만든 음악·효과음은 각 제작자의 조건을 따라 주세요. 포함 자료와 출처는 [README-ASSETS.md](README-ASSETS.md), [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), [음원 안내](pack/audio/LICENSES.md)에 있습니다.

[엔진](https://github.com/totokim222111/super-ai-wars-engine) · [게임](https://github.com/totokim222111/super-ai-wars)

English: Copy the setup request above to an AI helper, or follow the game's manual setup instructions. PLEASE is a playful name: your interest alone means a lot. Our own work is free to use, change, share, and sell without conditions. Third-party works keep their own terms.
