# Karpathy Guidelines for Claude Code

LLM이 코드를 작성, 검토, 리팩터링할 때 자주 만드는 네 가지 실수를 줄이는 재사용 가능한 규칙 패키지입니다. Andrej Karpathy가 지적한 가정, 과도한 구현, 주변 코드 변경, 검증 부재 문제를 네 가지 출발 원칙으로 다룹니다.

NeoFun 버전은 이 네 원칙을 프로젝트에서 실제로 작동시키기 위해 판단 범위, 토큰 예산, 충돌 처리, 사전 읽기, 테스트 의도, 체크포인트, 기존 관례, 누락 없는 실패 보고까지 12규칙으로 확장했습니다.

## 패키지 구성

| 파일 | 용도 |
|---|---|
| `skills/karpathy-guidelines/SKILL.md` | Codex 등 Agent Skills 호환 환경의 재사용 스킬 |
| `.claude-plugin/` | Claude Code 플러그인과 marketplace 메타데이터 |
| `.cursor/rules/karpathy-guidelines.mdc` | Cursor 프로젝트 규칙 |
| `CLAUDE.md` | 프로젝트 루트에 두는 12규칙 템플릿 |
| `EXAMPLES.md` | 네 원칙을 적용하는 짧은 사례 |

## 설치

### Claude Code 플러그인

Claude Code 안에서 marketplace를 추가합니다.

```text
/plugin marketplace add bk20260126-code/neofun-claude-code-rules
```

그다음 플러그인을 설치합니다.

```text
/plugin install neofun-karpathy-guidelines@neofun-karpathy-guidelines
```

### 프로젝트별 규칙

`CLAUDE.md`를 사용할 프로젝트 루트에 복사합니다. 이미 프로젝트 규칙이 있으면 더 구체적인 규칙을 우선하고 충돌 문장만 조정합니다.

### Cursor

`.cursor/rules/karpathy-guidelines.mdc`를 사용할 프로젝트의 같은 경로에 복사합니다. 자세한 적용 방법은 [CURSOR.md](./CURSOR.md)를 확인합니다.

## 적용 기준

- 비자명한 작업에는 가정, 범위, 성공 조건을 먼저 밝힙니다.
- 요청 범위를 넘는 기능과 리팩터링을 넣지 않습니다.
- 변경 후 관련 테스트와 검증 결과를 보고합니다.
- Rule 6의 토큰 예산은 사용하는 모델과 작업 환경에 맞게 바꿉니다.

원칙의 출발점: [Andrej Karpathy의 LLM coding pitfalls 관찰](https://x.com/karpathy/status/2015883857489522876)

MIT License
