# vibium-js-api-test

A Claude Code skill that runs the [vibium](https://github.com/VibiumDev/vibium) JS API coverage test suite category by category against [vibium-test-js](https://github.com/lana-20/vibium-test-js).

## What it does

Runs `npx vitest` across 12 test categories covering every public method in the vibium JS language bindings. Labels each test `PASS`, `FAIL`, `BUG`, or `SKIP` and prints a summary table.

## Coverage

| Category | Tests | Methods |
|---|---|---|
| navigation | 7 | go, back, forward, reload, url, title, content |
| find | 13 | find (CSS/role/text/label/placeholder/alt/title/testid/xpath), findAll, element.find, element.findAll, fluent chaining |
| element-actions | 17 | click, dblclick, fill, type, clear, press, check, uncheck, selectOption, hover, focus, scrollIntoView, dispatchEvent, tap, dragTo, setFiles, element.waitUntil |
| element-read | 19 | text, innerText, html, value, attr, getAttribute, bounds, boundingBox, isVisible, isHidden, isEnabled, isChecked, isEditable, role, label, element.screenshot |
| wait | 5 | waitUntil.url, waitUntil.loaded, wait |
| evaluate | 7 | evaluate (string/number/boolean/object/flat array/nested array) |
| network | 8 | capture.response, capture.request, onRequest, onResponse, route.fulfill, route.continue, unroute, setHeaders |
| events | 8 | onDialog (alert/confirm/prompt), capture.dialog, capture.navigation, onConsole, onError, removeAllListeners |
| page-control | 16 | screenshot, pdf, scroll, setContent, addScript, addStyle, expose, setViewport, viewport, window, emulateMedia, a11yTree, frames, frame, bringToFront |
| browser-context | 10 | context.cookies, setCookies, clearCookies, storage, setStorage, clearStorage, addInitScript, browser.newPage, browser.newContext, browser.pages |
| input | 15 | keyboard.press/type/down/up, mouse.click/move/down/up/wheel, touch.tap, clock.install/fastForward/runFor/setFixedTime/setSystemTime/pauseAt/resume/setTimezone |
| recording | 3 | recording.start/stop, startChunk/stopChunk, startGroup/stopGroup |
| **TOTAL** | **128** | |

**Confirmed baseline:** 125 pass / 3 bug / 0 fail

## Known bugs

| Skipped test | Issue |
|---|---|
| `bug1: waitUntil(expression) …` (×2) in `api-wait.test.ts` | [VibiumDev/vibium#123](https://github.com/VibiumDev/vibium/issues/123) |
| `bug2: evaluate nested string[][] …` in `api-evaluate.test.ts` | [VibiumDev/vibium#124](https://github.com/VibiumDev/vibium/issues/124) |

## Installation

Copy `SKILL.md` to `~/.claude/skills/vibium-js-api-test/SKILL.md`.

Requires [vibium-test-js](https://github.com/lana-20/vibium-test-js) cloned locally and `VIBIUM_BIN_PATH` set to the vibium binary.

## Usage

```
/vibium-js-api-test              # run all 12 categories
/vibium-js-api-test navigation   # run one category
```
