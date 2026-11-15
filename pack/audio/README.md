# 소리 팩

이 폴더에 `pack.json`과 소리 파일을 두면 엔진이 불러온다. 팩이 없으면 효과음은 엔진이 합성한 소리로 나오고 음악은 없다.

## pack.json

```json
{
  "name": "기본 소리 팩",
  "sfx": {
    "hit": { "file": "sfx/hit.ogg", "gain": 0.9, "title": "타격", "author": "만든이", "license": "CC0", "source": "https://..." }
  },
  "bgm": {
    "battle": { "file": "bgm/battle.ogg", "loopStart": 12.48, "loopEnd": 96.0, "gain": 0.7, "title": "곡 이름", "author": "만든이", "license": "CC BY 4.0", "source": "https://..." }
  }
}
```

- `sfx`의 이름이 엔진의 효과음 이름과 같으면 합성음을 덮어쓴다: `cursor` `confirm` `important` `cancel` `deny` `text` `whoosh` `slash` `shot` `hit` `heavy` `explode` `charge` `flash` `gauge`. 다른 이름을 더해도 된다.
- `bgm`은 화면이나 대본이 이름으로 부른다. `loopStart`~`loopEnd`(초)를 적으면 도입부는 한 번만 나오고 그 구간만 되풀이된다. 안 적으면 곡 전체가 되풀이된다.
- 파일 형식은 ogg나 mp3. 효과음은 짧게(2초 안쪽), 음악은 128~160kbps면 충분하다.

## 라이선스 규칙

- **`license`와 `source`가 비어 있는 항목은 불러오지 않는다.** 출처를 모르는 소리가 섞이지 않게 하려는 것이다.
- 넣어도 되는 것: CC0, CC BY(크레딧 표기), 제작자가 "게임에 자유롭게 써도 된다"고 명시한 무료 소재.
- 넣으면 안 되는 것: 상용 게임에서 뽑아낸 소리(슈퍼로봇대전 원작의 효과음·음악 포함), 애니메이션 주제가의 편곡·MIDI, RPG 만들기(쯔꾸르) 기본 소재(그 툴로 만든 게임 안에서만 쓸 수 있다), 이용 조건을 확인할 수 없는 팬 소재.
- 엔진은 불러온 항목으로 크레딧 목록을 만든다(`Sound.credits()`). 진열장의 "소리" 화면에서 볼 수 있다.


## 승인 팩과 추가 항목

- 현재 SAW 팩은 승인된 S1~S4/M1~M13의 선별 음원 33개다. 원본 다운로드는 공개 폴더에 두지 않는다. 항목별 원본·자르기·파형 수치는 `audio-src/selection.json`, 공식 페이지·SHA256은 `audio-src/sources.json`, 라이선스는 이 폴더의 `LICENSES.md`와 `docs/v2-sound-sources.md`의 받은 결과에 있다.
- 새 효과음 이름: `beam`, `missile`, `transform`, `servo`, `alarm`, `levelup`. 파일이 없으면 기존과 같이 합성 레시피를 쓴다.
- `credit`은 화면에 표시할 명의다. author는 제작자 이름 그대로 둔다. 魔王魂 항목은 `author: "魔王魂"`, `credit: "音楽：魔王魂"`이며 모든 곡의 재인코딩 사실을 `modifications`와 LICENSES.md에 적었다.
- `loop: false`는 한번만 재생하는 징글이다. 생략하면 기존 전체/구간 반복이다. 반복 구간이 버퍼 밖이거나 역순이면 해당 항목을 건너뛴다.
- M1/M2는 도입+반복을 PCM으로 연결해 한 OGG로 만들었다. M1 loopStart=1.623945578, M2 loopStart=39.724149660초다. M2의 원본 `_loop.wav`가 도입, `_opening.wav`가 반복이다.
- 처리: `python -I -X utf8 tools/sound_build.py`, 문서/파형: `python -I -X utf8 tools/sound_report.py`. ffmpeg/ffprobe, Python numpy/Pillow가 있는 환경에서 쓴다. 내려받은 코드는 실행하지 않는다.
- 버스 음량은 첫 unlock부터 설정값을 따른다. 첫 입력 전에 대기한 음악을 시작하고, 같은 곡 요청은 재시작하지 않는다. 곡 전환은 기존 0.6초 크로스페이드이며 이전 소스는 페이드 뒤 종료한다. 없는 곡 요청은 경고만 남기고 현재 곡을 유지한다.

배포 파일은 승인 원본에서 MP3로 다시 인코딩했다. 파일 이름에 SHA256 앞 12자, pack.json에 원본 PCM 길이와 반복 지점을 기록했다. 원본·출처와 라이선스는 변경하지 않았다.

2026-11-13 승인 추가: 음악·징글 29곡(기존 13+추가 16), 효과음은 2026-11-14 일반·중요 선택 분리 후 21개입니다. 사용자 제공 원본의 해시를 확인한 뒤 `python -I tools/import_audio_themes.py`로 가져오고 `node tools/audio_themes.mjs`로 테마·장면 메타데이터를 배정합니다. `--check`는 공개 사본의 출처·선별·변환 기록과 파일만 읽으므로 다운로드 원본 없이 동작합니다. 원본을 실행하거나 추가로 내려받지 않습니다.
