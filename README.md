[README_SW4DX_LightingPort.md](https://github.com/user-attachments/files/34675173/README_SW4DX_LightingPort.md)
# SW4DX_LightingPort
전국무쌍4DX의 그래픽을 무쌍 오로치 3 느낌으로 개선합니다.
# SW4DX LightingPort v1.0

**전국무쌍4 DX(Samurai Warriors 4 DX) 화면·조명 개선 모드 (3DMigoto)**

무쌍오로치4(WARRIORS OROCHI 4)의 톤 곡선과 FXAA를 옮겨 오고, 부드러운 그림자·AO·블룸 개선·하늘 그라데이션을 더해서 "날것의 3D" 느낌이던 화면을 차분하고 고급스럽게 다듬는 모드입니다. 모델·텍스처·게임 데이터는 건드리지 않고 **화면 셰이더만** 바꿉니다.

A 3DMigoto shader mod for Samurai Warriors 4 DX (Steam, x64). It ports the Warriors Orochi 4 tonemap and FXAA and adds soft shadows, ambient occlusion, smoother bloom, star glare, sharpening and a sky gradient. Shaders only: no models, textures or game data are touched. English summary at the bottom.

---

## 주요 기능

| 효과 | 설명 | 기본값 |
|---|---|---|
| WO4 톤 | 무쌍오로치4에서 추출한 톤 곡선, 화이트 포인트, 채도 | 켜짐 |
| WO4 FXAA | 무쌍오로치4의 안티에일리어싱 | 켜짐 |
| WO4 색 보정 | 대비를 부드럽게, 뿌옇지 않게, 밝은 부분은 살짝 푸르게 | 켜짐 (1.0) |
| 부드러운 그림자 | 각진 그림자 경계를 부드럽게, 품질 1~5단계 | 켜짐 (품질 4) |
| AO | 주름, 발밑, 모서리에 은은한 접촉 그림자 (간접광에만 적용), 샘플 8~32개 5단계 | 켜짐 (0.6, 품질 5) |
| 블룸 부드럽게 | 덩어리지던 빛 번짐을 매끈하게 | 켜짐 |
| 스타 글레어 | 아주 밝은 반사점에 WO4식 X자 빛줄기, 미세한 색 번짐 포함 | 켜짐 (0.2, 품질 5) |
| 선명화 | AMD CAS(대비 적응형) 방식으로 텍스처 디테일 복원 | 켜짐 (0.5) |
| 하늘 그라데이션 | 하늘만 위로 갈수록 푸르게 (깊이로 하늘만 판별) | 켜짐 (0.5) |
| 갓레이 품질 | 빛줄기 샘플 수 1~5단계 | 켜짐 (품질 3) |
| 비네트 | 화면 모서리를 아주 살짝 어둡게 | 켜짐 (0.12) |

안개는 원본 그대로 둡니다.

---

## 필요한 것

- Steam판 **전국무쌍4 DX (Windows 64비트)**
- **3DMigoto 1.3.16** (이미 다른 3DMigoto 모드를 쓰고 있다면 그대로 사용)

### 3DMigoto 설치 (처음 쓰는 경우만)

1. 공식 배포처 [bo3b/3Dmigoto Releases](https://github.com/bo3b/3Dmigoto/releases)에서 `3Dmigoto-1.3.16.zip`을 받습니다.
2. 압축 안의 **`x64` 폴더 내용물**을 `SamuraiWarriors4DX.exe`가 있는 게임 폴더에 복사합니다.
3. 게임 폴더의 `d3dx.ini`를 메모장으로 열고 아래 두 가지를 확인합니다.
   - `[Include]` 섹션에 `include_recursive = Mods` 줄이 있어야 합니다. 앞에 `;`가 있으면 지웁니다.
   - `[Hunting]` 섹션의 `hunting=1`을 **`hunting=0`** 으로 바꿉니다. 화면에 개발용 표시가 뜨지 않게 하고, 단축키 충돌도 막습니다.

---

## 설치

1. 게임을 종료합니다.
2. 압축 파일을 **게임 폴더**(`SamuraiWarriors4DX.exe`가 있는 곳)에 그대로 풉니다.
   Steam 라이브러리에서 게임 우클릭 → 관리 → 로컬 파일 보기
3. 게임을 실행합니다.

압축을 풀면 아래처럼 들어갑니다.

```text
SAMURAI WARRIORS 4 DX/
├─ SamuraiWarriors4DX.exe
├─ ShaderFixes/
│  ├─ 92856dde7d9fd891-ps.txt   ← 이 모드 셰이더 6개
│  ├─ 00197c27f0b3db61-ps.txt
│  ├─ 1d00b5bed377e500-ps.txt
│  ├─ 7fe5d739b4cf9f19-ps.txt
│  ├─ e3943eaedb013586-ps.txt
│  └─ 39eaddb1c5016fc0-ps.txt
└─ Mods/
   └─ SW4DX_LightingPort/
      └─ LightingPort.ini        ← 설정 파일
```

> 압축을 풀 때 **"같은 이름의 파일이 있습니다"** 라고 나오면, 다른 모드가 같은 셰이더를 바꾸고 있다는 뜻입니다. 덮어쓰기 전에 그 파일을 백업하세요. 두 모드는 동시에 쓸 수 없습니다.
> (예전 버전의 이 모드를 덮어쓰는 경우는 그대로 덮어써도 됩니다. 설정을 바꿔 두었다면 `LightingPort.ini`만 미리 백업하세요.)

## 사용법

### 게임 중 단축키

**Shift 또는 Ctrl 중 하나**를 누른 채 F키를 누릅니다.

| 키 | 기능 |
|---|---|
| F3 / F4 | 밝기 - / + |
| F5 / F6 | 채도 - / + |
| F7 / F8 | 블룸 - / + |
| F11 | 그림자 진하기 (원본 → -15% → -25% → -35%) |
| F12 | 전체 효과 켜기/끄기 (원본 화면과 비교) |

단축키로 바꾼 값은 다음 실행 때도 유지됩니다 (`d3dx_user.ini`에 자동 저장).

### 세부 설정

`Mods\SW4DX_LightingPort\LightingPort.ini`를 메모장으로 열면 효과마다 한글 설명이 달려 있습니다.

- `1` = 켜기, `0` = 끄기
- 세기와 품질은 숫자로 조절
- 저장한 뒤 게임에서 **F10**을 누르면 바로 적용됩니다

자주 찾는 조절:

| 이럴 때 | 바꿀 값 |
|---|---|
| 그림자가 아직 각져 보임 | `$cfg_shadow_softness` 올리기 (0.4~0.5) |
| 그림자가 뿌옇게 번짐 | `$cfg_shadow_softness` 내리기 (0.2) |
| 대비가 세게 느껴짐 | `$cfg_wo4_grade_strength` 내리기 (0.5~0.6) |
| AO가 얼룩져 보임 | `$cfg_ao_radius` 0.025 또는 `$cfg_ao_strength` 0.4 |
| 프레임이 부족함 | `$cfg_ao_quality = 3`, `$cfg_star_quality = 3`, `$cfg_shadow_quality = 3` (그래도 부족하면 `$cfg_ao = 0`) |

### 잠시 끄기

`Mods\SW4DX_LightingPort` 폴더 이름을 `DISABLED_SW4DX_LightingPort`로 바꾸면 원본 화면으로 돌아갑니다. 설정 INI가 없으면 셰이더가 원본과 똑같이 동작하도록 만들었기 때문입니다. 다시 켜려면 이름을 원래대로 돌리면 됩니다.

---

## 삭제

게임 폴더에서 아래 파일을 지우면 원래대로 돌아갑니다. 3DMigoto와 다른 모드는 그대로 둡니다.

- `Mods\SW4DX_LightingPort` 폴더
- `ShaderFixes` 폴더 안의 아래 6개 해시로 시작하는 파일 (`-ps.txt`와 `-ps.bin` 모두)
  `92856dde7d9fd891`, `00197c27f0b3db61`, `1d00b5bed377e500`, `7fe5d739b4cf9f19`, `e3943eaedb013586`, `39eaddb1c5016fc0`

`ShaderFixes`의 다른 파일(help.ini 등)은 3DMigoto 파일이니 지우지 마세요.

## 호환성

| 대상 | 호환 | 설명 |
|---|---|---|
| 전국무쌍4 DX 한글패치 (dinput8.dll) | ✅ | 한글패치는 텍스트 데이터만, 이 모드는 화면 셰이더만 바꿔서 겹치지 않습니다 |
| 오리진 모드 등 DLL 방식 게임 모드 | ✅ | 게임 로직용 DLL은 렌더링과 무관합니다. 3DMigoto의 `d3dcompiler_46.dll`과 오리진의 `D3DCompiler_43.dll`은 서로 다른 파일입니다 |
| 다른 3DMigoto 의상·모델 모드 | ✅ | `Mods` 폴더에서 각자 독립적으로 로드됩니다 |
| 같은 화면 셰이더를 바꾸는 모드 | ⚠️ | 아래 해시를 쓰는 모드와는 동시에 쓸 수 없습니다. 압축 풀 때 덮어쓰기 경고가 나오면 이 경우입니다 |
| ReShade | ⚠️ | 같이 쓸 수는 있지만 톤·선명화·AO가 이중으로 걸리면 화면이 과해질 수 있습니다 |

**이 모드가 바꾸는 셰이더 (ShaderFixes)**

| 해시 | 용도 |
|---|---|
| `92856dde7d9fd891-ps` | 최종 화면 합성 |
| `00197c27f0b3db61-ps` | 최종 화면 합성 (피사계 심도 사용 장면) |
| `1d00b5bed377e500-ps` | 조명 + 그림자 + AO |
| `7fe5d739b4cf9f19-ps` | 조명 + 그림자 + AO (피부 쪽) |
| `e3943eaedb013586-ps` | 갓레이 |
| `39eaddb1c5016fc0-ps` | 갓레이 |

**다른 3DMigoto 모드 제작자 참고**

- IniParams **5~12번 슬롯**을 사용합니다. 같은 슬롯을 쓰는 모드와는 값이 섞일 수 있습니다.
- 단축키는 `Shift`/`Ctrl` 조합만 씁니다. 수식 키 없는 F키는 쓰지 않습니다.
- 3DMigoto 기본 설정에서 `hunting=1`이면 Ctrl+F8이 프레임 분석 키와 겹칠 수 있으니 `hunting=0`을 권장합니다.

---

## 문제 해결

- **효과가 전혀 안 보임**
  - `d3dx.ini`에 `include_recursive = Mods`가 있는지 확인하세요.
  - Shift+F12로 켜고 꺼 보세요.
- **화면이 깨짐 / 검은 화면**
  - 같은 셰이더를 바꾸는 다른 모드와 충돌하는 경우입니다.
  - `ShaderFixes`에 위 해시 파일이 이 모드 것인지 확인하세요. 파일 첫 줄에 `SW4DX_LightingPort`가 있으면 이 모드 파일입니다.
- **단축키가 안 먹음**: Shift나 Ctrl 중 하나만 누른 채로 F키를 누르세요. Shift와 Ctrl을 같이 누르면 작동하지 않습니다.
- **Steam 스크린샷 키 (F12)**: Shift+F12는 Steam 스크린샷과 같이 눌릴 수 있습니다. 거슬리면 Ctrl+F12를 쓰세요.

---

## English summary

**Install:** requires 3DMigoto 1.3.16. `d3dx.ini` must contain `include_recursive = Mods`, and `hunting=0` is recommended. Extract the archive into the game folder (next to `SamuraiWarriors4DX.exe`). If Windows asks to overwrite files in `ShaderFixes`, another mod replaces the same shaders: back those files up first.

**Configure:** edit `Mods\SW4DX_LightingPort\LightingPort.ini` (1 = on, 0 = off), then press F10 in game.

**Hotkeys** (Shift *or* Ctrl + key):

| Key | Function |
|---|---|
| F3/F4 | Brightness |
| F5/F6 | Saturation |
| F7/F8 | Bloom |
| F11 | Shadow darkness |
| F12 | All effects on/off |

**Disable:** rename the mod folder to `DISABLED_SW4DX_LightingPort`; the shaders then behave exactly like vanilla.

**Uninstall:** delete `Mods\SW4DX_LightingPort` and the six `ShaderFixes\<hash>-ps.txt/.bin` files listed above.

**Uses:** the six shader hashes listed above and IniParams slots 5 to 12.

---

## 크레딧 / Credits

- 3DMigoto by bo3b, DarkStarSword and contributors
- 원본 게임 셰이더 © KOEI TECMO GAMES. 이 모드는 비공식 팬 모드이며, 원본 셰이더를 수정한 파일만 포함합니다.
- Unofficial fan mod. Contains only modified versions of the game's shaders. Samurai Warriors / Warriors Orochi © KOEI TECMO GAMES.
