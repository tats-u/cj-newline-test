# Newline => space or truncated?

https://tats-u.github.io/cj-newline-test/

## What's this?

This site is created to test what kind of characters the current browser truncates a newline between. [The CSS specification](https://drafts.csswg.org/css-text-4/#line-break-transform) discourages browsers from converting newline between Chinese or Japanese characters to space.

> 這個段落是那麼長，\
> 在一行寫不行。最好\
> 用三行寫。

The above text must be “這個段落是那麼長，在一行寫不行。最好用三行寫。”

You can access to check test cases [here](https://wpt.fyi/results/css/css-text/line-breaking?label=experimental&label=master&aligned&q=segment-break-transformation-rules-). Those only Firefox passes are what we are discussing.

## How should I use this?

Once you press “Go”, the following two texts will be generated and compared for their rendered widths:

- [Target Character][LF][Partner Character]
- [Target Character][Partner Character]

[LF] means a newline. Every character in the range U+2E80–U+1FFF is checked as “[Target Character]”, and “[Partner Character]” can be one of:

- [Target Character] (when you choose “Same character”)
- Han (set as “測”)
- Fullwidth Alphabet (set as “Ｆ”)
- Halfwidth Katakana (set as “ﾃ”)
- Hangul (set as “테”)
- Alphabet (set as “n”)

The result shows what characters truncate a newline next to them. Ideally, only a newline between Chinese or Japanese characters should be truncated. Note that Korean characters behave like Halfwidth alphabets.

## What browser should I use?

If the browser asserts that it supports this feature, you can use it. Firefox has supported it for a long time.

You can check the bug tracker of Chromium (Chrome) and WebKit (Safari) in:

- Chromium: [#1](https://issues.chromium.org/issues/40069685) / [#2](https://issues.chromium.org/issues/40774934)
- [WebKit](https://bugs.webkit.org/show_bug.cgi?id=260857)

## Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## Result in Firefox

Version 131, Same Character

A newline is truncated if surrounded by the following characters:

- U+2E80–U+2E99
- U+2E9B–U+2EF3
- U+2F00–U+2FD5
- U+2FF0–U+2FFB
- U+3000–U+302D
- U+3031–U+303C
- U+303E
- U+3041–U+3096
- U+3099–U+30FF
- U+3105–U+312F
- U+3190–U+31E3
- U+31F0–U+31FF
- U+3220–U+3247
- U+3250–U+325F
- U+327F–U+3296
- U+3298
- U+329A–U+4DBF
- U+4E00–U+A48C
- U+A490–U+A4C6
- U+F900–U+FAFF
- U+FE10–U+FE19
- U+FE30–U+FE52
- U+FE54–U+FE66
- U+FE68–U+FE6B
- U+FF01–U+FF9F
- U+FFE0–U+FFE6
- U+FFE8–U+FFEE
- U+16FE0–U+16FE4
- U+16FF0–U+16FF1
- U+17000–U+187F7
- U+18800–U+18CD5
- U+18D00–U+18D08
- U+1AFF0–U+1AFF3
- U+1AFF5–U+1AFFB
- U+1AFFD–U+1AFFE
- U+1B000–U+1B122
- U+1B132
- U+1B150–U+1B152
- U+1B155
- U+1B164–U+1B167
- U+1B170–U+1B2FB
- U+1F200
- U+1F210–U+1F219
- U+1F21B–U+1F22E
- U+1F230–U+1F231
- U+1F23B
- U+1F240–U+1F248
- U+1F260–U+1F265
