# Claude Productivity

[Claude Code](https://docs.anthropic.com/en/docs/claude-code)를 활용한 생산성 향상 도구 모음입니다.

## Projects

### 🛠 Skills & Commands

Claude Code CLI에서 사용하는 커스텀 Skills과 Slash Commands입니다.

### 📊 Dashboard (예정)

로컬에서 실행 중인 Claude Code 세션들을 자동 감지하여 상태를 한눈에 보여주고, 모든 세션의 작업 로그를 로컬에 누적 적재하여 히스토리 추적이 가능한 대시보드입니다.

- **실시간 세션 모니터링** — 🟢 작업중 / 🟡 입력대기 / ⚪ 완료 / 🔴 에러
- **작업 로그 적재** — Claude Code hooks를 통해 세션 이벤트를 자동 수집·영구 보관
- **세션 상세 뷰** — 대화 로그 확인, 작업 요약, 변경 파일 목록
- **하이브리드 UI** — `claude-dash` CLI + 웹 대시보드

---

## Skills

자동으로 트리거되는 스킬입니다. `~/.claude/skills/` 에 배치합니다.

| Skill | 설명 | 파일 |
|-------|------|------|
| **alarm-on** | Claude 응답 완료 시 알림을 켭니다 (hooks 기반) | [SKILL.md](skills/alarm-on/SKILL.md) |
| **alarm-off** | Claude 응답 완료 알림을 끕니다 | [SKILL.md](skills/alarm-off/SKILL.md) |
| **alarm-volume** | 알림 레벨을 설정합니다 (1=무음, 2=기본, 3=사이렌) | [SKILL.md](skills/alarm-volume/SKILL.md) |

## Slash Commands

`/명령어`로 직접 호출하는 커맨드입니다. `~/.claude/commands/` 에 배치합니다.

| Command | 설명 | 파일 |
|---------|------|------|
| `/schedule` | Google Calendar + Apple Reminders 일정을 조회하고 브리핑합니다 | [schedule.md](commands/schedule.md) |
| `/schedule-add` | 자연어로 일정을 등록합니다 (캘린더 + 리마인더 동시 등록) | [schedule-add.md](commands/schedule-add.md) |
| `/clarify` | 소크라테스식 질문을 통해 모호한 아이디어를 구체화합니다 | [clarify.md](commands/clarify.md) |
| `/obsidian` | 현재 대화 내용을 분석하여 Obsidian vault에 구조화된 노트로 정리합니다 | [obsidian.md](commands/obsidian.md) |

## 설치

원하는 파일을 복사하여 사용합니다.

```bash
# Skills
cp -r skills/alarm-on ~/.claude/skills/
cp -r skills/alarm-off ~/.claude/skills/
cp -r skills/alarm-volume ~/.claude/skills/

# Commands
cp commands/schedule.md ~/.claude/commands/
cp commands/schedule-add.md ~/.claude/commands/
cp commands/clarify.md ~/.claude/commands/
cp commands/obsidian.md ~/.claude/commands/
```

> `/schedule`, `/schedule-add`, `/obsidian`은 MCP 서버 연동이 필요합니다 (google-calendar, apple-reminders, obsidian).

## 요구사항

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code)
- `/schedule`, `/schedule-add` — [google-calendar MCP](https://github.com/nspady/google-calendar-mcp), [apple-reminders MCP](https://github.com/pzingg/apple-reminders-mcp)
- `/obsidian` — [Obsidian Local REST API](https://github.com/coddingtonbear/obsidian-local-rest-api) + Obsidian MCP

## License

MIT
