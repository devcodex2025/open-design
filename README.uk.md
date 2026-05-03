# Open Design

> **Альтернатива з відкритим кодом до [Claude Design][cd].** Локально-перший, розгортується в web, BYOK на кожному рівні — **13 CLI агентів для кодування** автоматично виявляються у вашому `PATH` (Claude Code, Codex, Devin for Terminal, Cursor Agent, Gemini CLI, OpenCode, Qwen, GitHub Copilot CLI, Hermes, Kimi, Pi, Kiro, Mistral Vibe) стають механізмом дизайну, керуються **31 компонуваною навичкою** та **72 системами дизайну комерційного класу**. Немає CLI? OpenAI-сумісний BYOK проксі — це той же цикл без spawn.

<p align="center">
  <img src="docs/assets/banner.png" alt="Open Design — editorial cover: design with the agent on your laptop" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/nexu-io/open-design/stargazers"><img alt="Stars" src="https://img.shields.io/github/stars/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=ffd700&logo=github&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/network/members"><img alt="Forks" src="https://img.shields.io/github/forks/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=2ecc71&logo=github&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/issues"><img alt="Issues" src="https://img.shields.io/github/issues/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=ff6b6b&logo=github&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/pulls"><img alt="Pull Requests" src="https://img.shields.io/github/issues-pr/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=9b59b6&logo=github&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=3498db&logo=github&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/commits/main"><img alt="Commit activity" src="https://img.shields.io/github/commit-activity/m/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=e67e22&logo=git&logoColor=white" /></a>
  <a href="https://github.com/nexu-io/open-design/commits/main"><img alt="Last commit" src="https://img.shields.io/github/last-commit/nexu-io/open-design?style=for-the-badge&labelColor=0d1117&color=8e44ad&logo=git&logoColor=white" /></a>
</p>

<p align="center">
  <a href="https://github.com/nexu-io/open-design/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/nexu-io/open-design?style=flat-square&color=blueviolet&label=release&include_prereleases" /></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache%202.0-blue.svg?style=flat-square" /></a>
  <a href="#підтримувані-агенти-для-кодування"><img alt="Agents" src="https://img.shields.io/badge/agents-13%20CLIs%20%2B%20BYOK%20proxy-black?style=flat-square" /></a>
  <a href="#системи-дизайну"><img alt="Design systems" src="https://img.shields.io/badge/design%20systems-72-orange?style=flat-square" /></a>
  <a href="#навички"><img alt="Skills" src="https://img.shields.io/badge/skills-31-teal?style=flat-square" /></a>
  <a href="QUICKSTART.md"><img alt="Quickstart" src="https://img.shields.io/badge/quickstart-3%20commands-green?style=flat-square" /></a>
</p>

<p align="center"><a href="README.md">English</a> · <a href="README.de.md">Deutsch</a> · <a href="README.zh-CN.md">简体中文</a> · <a href="README.zh-TW.md">繁體中文</a> · <a href="README.ko.md">한국어</a> · <a href="README.ja-JP.md">日本語</a> · <b>Українська</b> · العربية</p>

---

## Чому це існує

[Claude Design][cd] від Anthropic (випущено 17.04.2026, Opus 4.7) показав, що відбувається, коли LLM припиняє писати прозу й починає поставляти артефакти дизайну. Це стало вірусним — і залишилось закритим кодом, тільки платним, тільки хмарним, прив'язаним до моделі Anthropic та навичок Anthropic. Немає касси, немає self-hosting, немає Vercel deploy, немає зміни на свого власного агента.

**Open Design (OD) — це альтернатива з відкритим кодом.** Той же цикл, той же artifact-first менталітет, але без lock-in. Ми не поставляємо агента — найсильніші агенти для кодування вже живуть на вашому ноутбуці. Ми підключаємо їх до workflow дизайну, керованого навичками, що працює локально за допомогою `pnpm tools-dev`, може розгорнути веб-шар на Vercel, і залишається BYOK на кожному рівні.

Введіть `make me a magazine-style pitch deck for our seed round`. Інтерактивна форма запитань з'являється до того, як модель навіть імпровізує один піксель. Агент вибирає один із п'яти курованих візуальних напрямків. Живий план `TodoWrite` потокує в UI. Демон будує реальну папку проекту на диску з seed шаблоном, бібліотекою макетів і контрольним списком self-check. Агент читає їх — перевірка перед польотом обов'язкова — запускає п'яти-розмірну критику проти свого власного виходу й видає один `<artifact>`, який рендериться в пісочниці iframe через кілька секунд.

Це не "AI спробує щось спроектувати". Це AI, яка була навчена prompt stack, щоб поводитись як старший дизайнер з робочою файловою системою, детермінованою бібліотекою палітри та культурою контрольного списку — саме той стандарт, який встановив Claude Design, але відкритий і ваш.

OD стоїть на плечах чотирьох проектів з відкритим кодом:

- [**`alchaincyf/huashu-design`**](https://github.com/alchaincyf/huashu-design) — компас філософії дизайну. Workflow молодого дизайнера, протокол бренд-активів з 5 кроками, контрольний список anti-AI-slop, п'яти-розмірна self-critique та ідея "5 шкіл × 20 філософій дизайну" за нашим direction picker — все конденсоване в [`apps/web/src/prompts/discovery.ts`](apps/web/src/prompts/discovery.ts).
- [**`op7418/guizang-ppt-skill`**](https://github.com/op7418/guizang-ppt-skill) — режим presentations. Включена без змін під [`skills/guizang-ppt/`](skills/guizang-ppt/) із збереженою оригінальною ліцензією; макети в стилі журналу, WebGL герой, контрольні списки P0/P1/P2.
- [**`OpenCoworkAI/open-codesign`**](https://github.com/OpenCoworkAI/open-codesign) — UX північна зірка й наш найближчий партнер. Перша альтернатива Claude Design з відкритим кодом. Ми запозичили цикл streaming-artifact, шаблон preview sandboxed-iframe (vendored React 18 + Babel), live agent panel (todos + tool calls + interruptible generation) та п'ять форматів експорту (HTML / PDF / PPTX / ZIP / Markdown). Ми навмисно розходимось за формою — вони настільна Electron app з bundled [`pi-ai`][piai]; ми веб-app + локальний daemon, яка делегує вашому наявному CLI.
- [**`multica-ai/multica`**](https://github.com/multica-ai/multica) — архітектура daemon та runtime. Виявлення агента PATH-scan, локальний daemon як єдиний привілейований процес, світогляд agent-as-teammate.

## Одним поглядом

| | Що ви отримуєте |
|---|---|
| **CLI агентів для кодування (13)** | Claude Code · Codex CLI · Devin for Terminal · Cursor Agent · Gemini CLI · OpenCode · Qwen Code · GitHub Copilot CLI · Hermes (ACP) · Kimi CLI (ACP) · Pi (RPC) · Kiro CLI (ACP) · Mistral Vibe CLI (ACP) — автоматично виявляються на `PATH`, одночисельний swap |
| **BYOK fallback** | OpenAI-сумісний проксі за адресою `/api/proxy/stream` — вставте `baseUrl` + `apiKey` + `model` і будь-який постачальник (Anthropic-via-OpenAI, DeepSeek, Groq, MiMo, OpenRouter, ваш self-hosted vLLM, або будь-який інший OpenAI-сумісний провайдер) стає механізмом. Внутрішня IP/SSRF заблокована на краю daemon. |
| **Системи дизайну вбудовані** | **129** — 2 hand-authored starter + 70 систем продукту (Linear, Stripe, Vercel, Airbnb, Tesla, Notion, Anthropic, Apple, Cursor, Supabase, Figma, Xiaohongshu, …) з [`awesome-design-md`][acd2], плюс 57 навичок дизайну з [`awesome-design-skills`][ads] додано безпосередньо під `design-systems/` |
| **Навички вбудовані** | **31** — 27 у режимі `prototype` (web-prototype, saas-landing, dashboard, mobile-app, gamified-app, social-carousel, magazine-poster, dating-web, sprite-animation, motion-frames, critique, tweaks, wireframe-sketch, pm-spec, eng-runbook, finance-report, hr-onboarding, invoice, kanban-board, team-okrs, …) + 4 у режимі `deck` (`guizang-ppt` · `simple-deck` · `replit-deck` · `weekly-update`). Згруповані у picker за `scenario`: design / marketing / operation / engineering / product / finance / hr / sale / personal. |
| **Медіа генерація** | Поверхні Image · video · audio поставляються разом з циклом дизайну. **gpt-image-2** (Azure / OpenAI) для плакатів, аватарів, інфографіки, ілюстрованих карт · **Seedance 2.0** (ByteDance) для кінематографічних 15-секундних text-to-video та image-to-video · **HyperFrames** ([heygen-com/hyperframes](https://github.com/heygen-com/hyperframes)) для HTML→MP4 motion graphics (product reveals, kinetic typography, data charts, social overlays, logo outros). **93** готових до репліки підказки — 43 gpt-image-2 + 39 Seedance + 11 HyperFrames — під [`prompt-templates/`](prompt-templates/), з preview thumbnails та атрибуцією джерела. Той же chat surface як код; виходить реальний `.mp4` / `.png` chip у робочий простір проекту. |
| **Візуальні напрями** | 5 курованих шкіл (Editorial Monocle · Modern Minimal · Warm Soft · Tech Utility · Brutalist Experimental) — кожна поставляється детермінованою палітрою OKLch + font stack ([`apps/web/src/prompts/directions.ts`](apps/web/src/prompts/directions.ts)) |
| **Кадри пристроїв** | iPhone 15 Pro · Pixel · iPad Pro · MacBook · Browser Chrome — пікселем точні, спільні під [`assets/frames/`](assets/frames/) |
| **Agent runtime** | Локальний daemon запускає CLI у вашій папці проекту — агент отримує справжні `Read`, `Write`, `Bash`, `WebFetch` проти справжнього середовища на диску, з Windows `ENAMETOOLONG` fallbacks (stdin / prompt-file) у кожному адаптері |
| **Імпорти** | Перенесіть [Claude Design][cd] export ZIP на вікно приватних користувачів — `POST /api/import/claude-design` розбирає його на справжній проект, щоб ваш агент міг продовжувати там, де Anthropic закінчився |
| **Постійність** | SQLite за адресою `.od/app.sqlite`: projects · conversations · messages · tabs · saved templates. Пересніть завтра, todo card і відкриті файли саме там, де ви їх залишили. |
| **Життєвий цикл** | Одна точка входу: `pnpm tools-dev` (start / stop / run / status / logs / inspect / check) — завантажує daemon + web (+ desktop) під типізованими sidecar stamps |
| **Desktop** | Опціональна Electron shell із sandboxed renderer + sidecar IPC (STATUS / EVAL / SCREENSHOT / CONSOLE / CLICK / SHUTDOWN) — керує `tools-dev inspect desktop screenshot` для E2E |
| **Розгортувати до** | Локально (`pnpm tools-dev`) · Vercel web layer · packaged Electron (placeholder, in-flight) |
| **Ліцензія** | Apache-2.0 |

[acd2]: https://github.com/VoltAgent/awesome-design-md
[ads]: https://github.com/bergside/awesome-design-skills

## Демонстрація

<table>
<tr>
<td width="50%">
<img src="docs/screenshots/01-entry-view.png" alt="01 · Entry view" /><br/>
<sub><b>Вид входу</b> — виберіть навичку, виберіть систему дизайну, введіть brief. Та сама поверхня для прототипів, presentations, мобільних додатків, dashboards та редакційних сторінок.</sub>
</td>
<td width="50%">
<img src="docs/screenshots/02-question-form.png" alt="02 · Turn-1 discovery form" /><br/>
<sub><b>Форма discovery Turn-1</b> — до того, як модель напише піксель, OD блокує brief: surface, audience, tone, brand context, scale. 30 секунд радіо краще, ніж 30 хвилин редиректів.</sub>
</td>
</tr>
<tr>
<td width="50%">
<img src="docs/screenshots/03-direction-picker.png" alt="03 · Direction picker" /><br/>
<sub><b>Вибір напрямку</b> — коли користувач не має бренду, агент видає другу форму з 5 курованими напрямами (Monocle / Modern Minimal / Tech Utility / Brutalist / Soft Warm). Один click радіо → детермінована палітра + font stack, без model freestyle.</sub>
</td>
<td width="50%">
<img src="docs/screenshots/04-todo-progress.png" alt="04 · Live todo progress" /><br/>
<sub><b>Живий прогрес todo</b> — план агента потокує як live card. `in_progress` → `completed` оновлення приходять в реальному часі. Користувач може дешево перенаправити в польоті.</sub>
</td>
</tr>
<tr>
<td width="50%">
<img src="docs/screenshots/05-preview-iframe.png" alt="05 · Sandboxed preview" /><br/>
<sub><b>Попередній перегляд в пісочниці</b> — кожен `<artifact>` рендериться в чистому srcdoc iframe. Редаговується на місці через файловий workspace; завантажується як HTML, PDF, ZIP.</sub>
</td>
<td width="50%">
<img src="docs/screenshots/06-design-systems-library.png" alt="06 · 72-system library" /><br/>
<sub><b>72-система бібліотека</b> — кожна система продукту показує своїм 4-колірна підпис. Натисніть для повного `DESIGN.md`, сітки зразків та live showcase.</sub>
</td>
</tr>
<tr>
<td width="50%">
<img src="docs/screenshots/07-magazine-deck.png" alt="07 · Magazine deck" /><br/>
<sub><b>Режим Deck (guizang-ppt)</b> — bundled [`guizang-ppt-skill`][guizang] падає без змін. Макети журналу, WebGL герой backgrounds, однофайловий HTML output, PDF export.</sub>
</td>
<td width="50%">
<img src="docs/screenshots/08-mobile-app.png" alt="08 · Mobile prototype" /><br/>
<sub><b>Мобільний прототип</b> — пікселем точна iPhone 15 Pro chrome (Dynamic Island, status bar SVGs, home indicator). Мультиекранні прототипи використовують спільні `/frames/` активи, тому агент ніколи не перерисовує телефон.</sub>
</td>
</tr>
</table>

## Швидкий старт

Для запуску Open Design локально:

```bash
# Клонуйте репозиторій
git clone https://github.com/nexu-io/open-design.git
cd open-design

# Встановіть залежності
pnpm install

# Запустіть локальний dev server
pnpm tools-dev
```

Браузер автоматично відкриється на `http://localhost:17573`. Залежно від вашої конфігурації системи, можливо, вам потрібно буде налаштувати:

- **Local CLI mode**: Переконайтесь, що ви маєте встановлений один із підтримуваних агентів (Claude Code, Codex, тощо) у вашому `PATH`.
- **API mode**: Вставте свій API-ключ Anthropic у настройки.

Для отримання докладнішої інформації див. [QUICKSTART.md](QUICKSTART.md).

## Навички

**31 навичка входить до комплекту.** Кожна — це папка під [`skills/`](skills/), яка слідує Claude Code [`SKILL.md`][skill] конвенції з розширеним `od:` frontmatter, який демон розбирає дослівно — `mode`, `platform`, `scenario`, `preview.type`, `design_system.requires`, `default_for`, `featured`, `fidelity`, `speaker_notes`, `animations`, `example_prompt` ([`apps/daemon/src/skills.ts`](apps/daemon/src/skills.ts)).

Два верхніх рівні **режимів** займають каталог: **`prototype`** (27 навичок — все, що рендериться як артефакт однієї сторінки, від журнального landing до екрана телефону до PM spec doc) та **`deck`** (4 навички — horizontal-swipe presentations з deck-framework chrome). Поле **`scenario`** — це те, як picker групує їх: `design` · `marketing` · `operation` · `engineering` · `product` · `finance` · `hr` · `sale` · `personal`.

## Системи дизайну

**72 системи дизайну** доступні з коробки — від провідних продуктів (Linear, Stripe, Vercel, Airbnb, Tesla) до брендів (Apple, Notion, Figma). Кожна система поставляється з:

- Палітрою кольорів
- Типографією
- Компонентами
- Повним файлом `DESIGN.md` з документацією

Виберіть одну як натхнення, коли створюєте новий проект.

## Вимоги

- **Node.js**: ~24
- **pnpm**: 10.33.2 або більше (з Corepack)
- **CLI агент** для локального режиму: один з Claude Code, Codex, Cursor Agent, Gemini CLI, OpenCode, Qwen, GitHub Copilot CLI, тощо.
- **API ключ Anthropic** для режиму BYOK API (необов'язково)

## Ліцензія

Open Design випущений під [Apache License 2.0](LICENSE).

## Контрибуція

Ми вітаємо контрибуції! Сміливо відкривайте issues, submit pull requests й ділітесь вашими ідеями.

Для отримання докладнішої інформації див. [CONTRIBUTING.md](CONTRIBUTING.md).

## Посилання

- **Веб-сайт**: https://github.com/nexu-io/open-design
- **Документація**: [docs/](docs/)
- **Швидкий старт**: [QUICKSTART.md](QUICKSTART.md)

[cd]: https://claude.ai/design
[piai]: https://github.com/pi-ai/pi-ai
[skill]: https://github.com/antonsten/claude-code-skill-template/blob/main/SKILL.md
[guizang]: https://github.com/op7418/guizang-ppt-skill
