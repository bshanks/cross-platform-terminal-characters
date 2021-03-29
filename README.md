<img src="https://raw.githubusercontent.com/ehmicky/design/main/cross-platform/cross-platform.svg?sanitize=true" width="500"/>

[![Build](https://github.com/ehmicky/cross-platform-terminal-characters/workflows/Build/badge.svg)](https://github.com/ehmicky/cross-platform-terminal-characters/actions)
[![Node](https://img.shields.io/node/v/cross-platform-terminal-characters.svg?logo=node.js)](https://www.npmjs.com/package/cross-platform-terminal-characters)
[![Twitter](https://img.shields.io/badge/%E2%80%8B-twitter-4cc61e.svg?logo=twitter)](https://twitter.com/intent/follow?screen_name=ehmicky)
[![Medium](https://img.shields.io/badge/%E2%80%8B-medium-4cc61e.svg?logo=medium)](https://medium.com/@ehmicky)

All the characters that work on most terminals and most operating systems.

# Background

While [ASCII characters](https://en.wikipedia.org/wiki/ASCII) display correctly
on all terminals, this is not the case of all characters. When building a
terminal application or tool, it is common to experience cross-platform issues
like:

<img src="https://raw.githubusercontent.com/ehmicky/cross-platform-terminal-characters/main/invalid_terminal_characters.png" width="259"/>

The main reasons are:

- The terminal font might not include this specific character.
- The terminal encoding may not support
  [Unicode](https://en.wikipedia.org/wiki/Unicode). For example,
  [`cmd.exe`](https://en.wikipedia.org/wiki/Cmd.exe) on Windows often use
  specific encodings like [CP437](https://en.wikipedia.org/wiki/Code_page_437),
  [CP850](https://en.wikipedia.org/wiki/Code_page_850) or
  [Windows-1252](https://en.wikipedia.org/wiki/Windows-1252).
- The application might not be properly converting encodings when reading or
  writing terminal characters.

The first two points can be solved by using characters known to display
correctly on most terminals and environments.

This repository contains a list of those characters:

- in this [`README.md`](#list-of-characters)
- as a [`characters.txt` file](characters.txt)
- as a [binary](#cli) printing the full list
- as a [Node.js module](#api) for programmatic usage

# List of characters

The following characters work on most terminals. This was tested on:

- Ubuntu 20.10, Gnome terminal 3.38.0
- macOS 10.14, terminal.app 2.9
- Windows 10.0.17763, cmd.exe (CP850)
- VSCode 1.54.3 terminal (xterm.js)
- Chrome web browser on Andriod (Chrome version 89.0.4389.105, Android 11 Build RQA.210305.006)

Those terminals are sufficient to catch most cross-platform issues. However, if
some characters listed below do not display correctly on your terminal, please
submit an issue to add your terminal.

When the character is displayed, its
[Unicode codepoint](https://en.wikipedia.org/wiki/Code_point) is shown above it.

## ASCII

Characters with [Unicode codepoints](https://en.wikipedia.org/wiki/Code_point)
[`0020-007f`](<https://en.wikipedia.org/wiki/Basic_Latin_(Unicode_block)>) work
on all terminals.

[Control characters](https://en.wikipedia.org/wiki/Control_character)
`0000-001f` and `0080-009f` have varying levels of support. However, the most
commonly used ones work on all terminals.

## Western languages

Characters with [Unicode codepoints](https://en.wikipedia.org/wiki/Code_point)
`00a0-058f` and `1d00-1fff` work on most terminals. They include:

- [latin alphabet](<https://en.wikipedia.org/wiki/Latin-1_Supplement_(Unicode_block)>)
- [greek/coptic](https://en.wikipedia.org/wiki/Greek_and_Coptic),
  [cyrillic](<https://en.wikipedia.org/wiki/Cyrillic_(Unicode_block)>),
  [armenian alphabets](<https://en.wikipedia.org/wiki/Armenian_(Unicode_block)>)
- [phonetic alphabet](https://en.wikipedia.org/wiki/IPA_Extensions)
- [accents / diacritical marks](https://en.wikipedia.org/wiki/Combining_Diacritical_Marks)

## Box drawing

```
2588 2593 2592 2591
██   ▓▓   ▒▒   ░░
258c 2590 2580 2584
▌▌   ▐▐   ▀▀   ▄▄
25ac 25a0 25aa 25a1 25ab
▬▬   ■■   ▪▪   □□   ▫▫

2500 2012 2014 2015 2501 2550
─    ‒    —    ―    ━    ═

2504 2505 2508 2509 254c 254d
┄┄   ┅┅   ┈┈   ┉┉   ╌╌   ╍╍
2212 2574 2013 2010 2578 2576
−−   ╴╴   ––   ‐‐   ╸╸   ╶╶

2502 2503 2551 2016 2506 2507
│    ┃    ║    ‖    ┆    ┇
250a 205e 250b 254e 254f 2575
┊    ⁞    ┋    ╎    ╏    ╵
2579 2577 257b 257d 257f
╹    ╷    ╻    ╽    ╿

250c 256d 250f 250d
┌    ╭    ┏    ┍
250e 2554 2552 2553
┎    ╔    ╒    ╓
2510 256e 2513 2511
┐    ╮    ┓    ┑
2512 2557 2555 2556
┒    ╗    ╕    ╖
2514 2570 2517 2515
└    ╰    ┗    ┕
2516 255a 2558 2559
┖    ╚    ╘    ╙
2518 256f 251b 2519
┘    ╯    ┛    ┙
251a 255d 255b 255c
┚    ╝    ╛    ╜
251c 2523 251d 251e 251f 2520
├    ┣    ┝    ┞    ┟    ┠
2521 2522 2560 255e 255f
┡    ┢    ╠    ╞    ╟
2524 252b 2525 2526 2527 2528
┤    ┫    ┥    ┦    ┧    ┨
2529 252a 2563 2561 2562
┩    ┪    ╣    ╡    ╢
252c 2533 252d 252e 252f 2530
┬    ┳    ┭    ┮    ┯    ┰
2531 2532 2566 2564 2565
┱    ┲    ╦    ╤    ╥
2534 253b 2535 2536 2537 2538
┴    ┻    ┵    ┶    ┷    ┸
2539 253a 2569 2567 2568
┹    ┺    ╩    ╧    ╨
253c 254b 253d 253e 253f 2540
┼    ╋    ┽    ┾    ┿    ╀
2541 2542 2543 2544 2545 2546
╁    ╂    ╃    ╄    ╅    ╆
2547 2548 2549 254a
╇    ╈    ╉    ╊
256c 256a 256b
╬    ╪    ╫

2573 2572 2571 2044 2215
╳    ╲     ╱    ⁄    ∕
```

## Geometrical shapes

```
2022
•
25cb 25cc 25cf
○    ◌    ●
25b2 25bc 25c4 25ba
▲    ▼    ◄    ►
25b4 25be 25c2 25b8
▴    ▾    ◂    ▸
2190 2191 2192 2193 2194 2195
←    ↑    →    ↓    ↔    ↕
2302 25ca 25d8 25d9
⌂    ◊    ◘    ◙
```

## Punctuation

```
2026 2030 203c
…    ‰    ‼

2018 2019 201a 201b
‘    ’    ‚    ‛
201c 201d 201e
“    ”    „
2032 2033 2039 203a
′    ″    ‹    ›
```

## Numbers and math

```
2248 2260 2261 2264 2265
≈    ≠    ≡    ≤    ≥

2202 2206 220f 2211 221a 221e
∂    ∆    ∏    ∑    √    ∞
221f 2229 222b 2310 2320 2321
∟    ∩    ∫    ⌐    ⌠    ⌡

215b 215c 215d 215e
⅛    ⅜    ⅝    ⅞

207f
ⁿ

24ea 2460 2461 2462 2463 2464
⓪   ①   ②    ③    ④    ⑤
2465 2466 2467 2468 2469 246a
⑥   ⑦    ⑧   ⑨    ⑩    ⑪
246b 246c 246d 246e 246f 2470
⑫   ⑬   ⑭   ⑮   ⑯   ⑰
2471 2472 2473
⑱   ⑲   ⑳
24ff 2776 2777 2778 2779 277a
⓿   ❶    ❷   ❸    ❹    ❺
277b 277c 277d 277e 277f 24ef
❻   ❼    ❽    ❾    ❿   ⓯
24f0 24f1 24f2 24f3 24f4
⓰   ⓱   ⓲    ⓳   ⓴
```

## Other symbols

```
2020 2021 263a 263b 263c 2736
†    ‡    ☺    ☻    ☼    ✶
2640 2642 2660 2663 2665 2666
♀    ♂    ♠    ♣    ♥    ♦
266a 266b 266f
♪    ♫    ♯

2105 2113 2116 2122 2126
℅    ℓ    №    ™    Ω
212e
℮

20a3 20a4
₣    ₤
20a7 20ab
₧    ₫
20ac
€
```

## Miscellaneous

```
fb00 fb01 fb02 fb03 fb04
ﬀ    ﬁ    ﬂ    ﬃ   ﬄ

fb13 fb14 fb15 fb16 fb17
ﬓ   ﬔ    ﬕ   ﬖ    ﬗ

```

# API

A Node module is available to retrieve the list of characters above or test
specific characters.

## Install

```
npm install cross-platform-terminal-characters
```

## Usage

```js
const {
  regex,
  codepoints,
  characters,
} = require('cross-platform-terminal-characters')

// false, i.e. cross-platform
console.log(regex.test('≈'))
// true, i.e. not cross-platform
console.log(regex.test('≐'))
// Remove not cross-platform characters, i.e. print `example ≈ test  text`
console.log('example ≈ test ≐ text'.replace(regex, ''))

// Array of codepoint integers: [0x0000, 0x0001, ..., 0xfb17]
console.log(codepoints)
// Array of single-character strings: ['\x00', '\x01', ..., 'ﬗ']
console.log(characters)
```

# CLI

The following command prints the full list of characters and their codepoints.

```
npx cross-platform-terminal-characters
```

If you don't have `npm` installed, the full list is available in
[`characters.txt`](characters.txt)

# See also

- [cross-platform-node-guide](https://github.com/ehmicky/cross-platform-node-guide):
  How to write cross-platform Node.js code.
- [figures](https://github.com/sindresorhus/figures): Unicode symbols with
  Windows `cmd.exe` fallbacks
- [log-symbols](https://github.com/sindresorhus/log-symbols): Colored symbols
  for various log levels

# Support

For any question, _don't hesitate_ to [submit an issue on GitHub](../../issues).

Everyone is welcome regardless of personal background. We enforce a
[Code of conduct](CODE_OF_CONDUCT.md) in order to promote a positive and
inclusive environment.

# Contributing

This project was made with ❤️. The simplest way to give back is by starring and
sharing it online.

If the documentation is unclear or has a typo, please click on the page's `Edit`
button (pencil icon) and suggest a correction.

If you would like to help us fix an error or add more information, please check
our [guidelines](CONTRIBUTING.md). Pull requests are welcome!

<!--
Thanks go to these wonderful people:

-->
<!-- ALL-CONTRIBUTORS-LIST:START -->
<!-- prettier-ignore -->
<!--
<table>
  <tr>
    <td align="center"><a href="https://twitter.com/ehmicky"><img src="https://avatars2.githubusercontent.com/u/8136211?v=4" width="100px;" alt="ehmicky"/><br /><sub><b>ehmicky</b></sub></a><br /><a href="https://github.com/ehmicky/cross-platform-terminal-characters/commits?author=ehmicky" title="Code">💻</a> <a href="#design-ehmicky" title="Design">🎨</a> <a href="#ideas-ehmicky" title="Ideas, Planning, & Feedback">🤔</a> <a href="https://github.com/ehmicky/cross-platform-terminal-characters/commits?author=ehmicky" title="Documentation">📖</a></td>
  </tr>
</table>

-->
<!-- ALL-CONTRIBUTORS-LIST:END -->
