---
theme: seriph
# background: https://source.unsplash.com/collection/94734566/1920x1080
background: /public/img/bg-2.jpg
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
title: Welcome to VIM
mdc: true
themeConfig:
    primary: '#5d8392'
---

# VIM

從新手到入門，掌握VIM的基礎操作

<!--

VIM是一款古老但功能強大的文本編輯器，
它被廣泛用於許多作業系統中，
並在程式開發者和系統管理員之間受到高度使用，
但同時， 由於它獨特的操作方式，
VIM也經常被認為有一定的學習曲線。

今天，我們的目標是打破這個迷思，
讓每一位參加者都從VIM的新手成長為入門者。
無論你是完全的初學者，還是之前已有一些VIM的經驗，
都希望這次的分享可以為你提供有價值的指導。

在接下來的時間裡，
我們將深入探討VIM的基礎操作，
從最基礎的移動和編輯，
到稍微進階的搜尋、
替換和配置等功能。
還會分享一些實用的技巧和資源，
幫助你在VIM的世界中更加得心應手。

-->

---
transition: fade-out
---

# VIM是什麼?

文本編輯器的一種 在終端機中運行 適用於多種作業系統

- 📝 **功能強大的編輯器** - 它擁有許多高級功能，例如語法高亮、自動完成、以及強大的搜尋和替換功能
- 🎨 **終端機內運行** - 主要在終端機中運行，讓你在沒有圖形界面的伺服器上也能順利工作
- 🧑‍💻 **模式化操作** - VIM擁有多種操作模式，如一般模式、插入模式和命令模式，這讓你能更高效地進行編輯
- 🤹 **跨平台兼容** - 包括Linux、macOS和Windows，這使得它成為一款真正的跨平台編輯器
- 🎥 **擴展性強** - 通過插件，擴展功能，使其成為一個完整的開發環境，適合各種語言和工具的編碼工作
- 📤 **鍵盤導向操作** - 這可以極大地提高編輯效率，一旦習慣，你可能會發現鼠標反而變得多餘
- 🛠 **低資源消耗** - 運行時資源消耗相對低。即使在資源有限的伺服器或老舊設備上，也能夠流暢運行

<br>
<br>


<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
今天我們要探討的是一款古老但仍然強大的工具：VIM。VIM有哪些特點使其在眾多編輯器中脫穎而出呢？

首先，當我們談到功能強大時，VIM絕對是頂尖的。它不只是一個文本編輯器，更是一個裝滿了語法高亮、自動完成和強大搜尋替換功能的寶盒。

接著，VIM的獨特之處在於它主要在終端機中運行。這使得在無GUI的伺服器上工作時，VIM成為一個不可或缺的工具。

而VIM的模式化操作設計，如一般模式、插入模式和命令模式，確保了用戶能夠專注於當前的任務，提高編輯效率。

不僅如此，VIM的跨平台特性意味著你可以在幾乎任何作業系統上使用它，從Linux到Windows，再到macOS。

對於需要更多自定義功能的你，VIM的擴展性能完美滿足。透過插件系統，VIM可以變身為一個功能齊全的開發環境。

再者，VIM特別鼓勵鍵盤操作，這種鍵盤導向的設計可以極大地提高你的工作效率。熟練後，你會發現鼠標在VIM世界中幾乎是不必要的。

最後，對於那些在資源有限的環境中工作的用戶，VIM的低資源消耗是一大賣點。它保證了即使在老舊硬體或資源受限的伺服器上，你也能得到流暢的使用體驗。

總之，VIM綜合了許多出色的特點，使其不僅適合初學者，更受到專業開發者的喜愛。透過今天的分享，希望你能更加了解這款強大的編輯器。

-->

---
layout: cover
---
<h1 v-click-hide>
Why I Use Vim 
</h1>
<div v-after  class="left-50 top-60 absolute text-5xl opacity-30 transform -rotate-10"> And Why You Should Too </div>

<!--
今天我想和大家分享一下，為什麼我選擇使用Vim，以及為什麼我認為你們也應該考慮使用它。

首先，讓我們談談組合按鍵。大家可能都經歷過這樣的情境：在一款編輯器或軟體中，想要完成某項操作，卻要按好幾次鍵，甚至需要移動手去點擊鼠標。這時候，Vim的組合按鍵優勢就體現出來了。在Vim中，大部分的操作都可以通過簡單、直觀的組合按鍵來完成。例如，你想刪除一行、複製一段或者快速跳轉到某個位置，只需要簡單的按鍵組合即可。

這帶領我們到了下一點：Vim的操作是快捷且精準的。因為Vim的按鍵設計都是基於提高效率和精確度，所以一旦你習慣了Vim的操作，你會發現自己的編輯速度和效率大大提高。

再來，我要談的是Vim的導航優勢。在許多編輯器中，導航文件可能需要滑鼠滾輪、箭頭鍵或其他不太直觀的方法。但在Vim中，你可以輕鬆地在文件之間、行之間甚至是字符之間快速移動。而且，Vim還提供了許多強大的搜尋和跳轉功能，讓你可以在大型文件或專案中迅速找到所需的位置。

總結一下，我選擇使用Vim，是因為它的效率、精確度和導航優勢。而我認為，無論你是一名開發者、寫手還是任何需要大量編輯文本的專業人士，Vim都是一款值得你學習和使用的工具。
-->


---
transition: slide-up
level: 2
layout: default
---

# 進入和退出VIM

Vim的門檻：如何進入與退出 - 各種保存與離開方法

|     |     |     |     |
|---------------- | --------------- | --------------- | --------------- |
|啟動     |     |     |     |
|vim     |     |     |     |
|退出     |     |     |     |
|  :q   | :q!    | :wq    | ZZ    |
| :x    |    |    |    |
|保存    |    |    |    |
| :w    |    |    |    |



<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
今天我要和大家講解的是如何進入和退出Vim，這是使用Vim的基礎，也是每位Vim用戶都必須掌握的技能。

首先，要進入Vim並開始編輯一個文件，你只需要在終端機中輸入 vim，後面跟著你想要編輯的文件名，例如 vim filename。這樣，Vim就會啟動，並打開名為filename的文件供你編輯。

當你完成文件的編輯，下一步自然是想要退出Vim。但在Vim中，這並不像其他的編輯器那樣簡單，因為Vim提供了多種退出方法，每種都有其特定的用途。

:q: 這是最基本的退出命令。如果你沒有對文件進行更改，輸入這個命令會直接退出Vim。
:q!: 如果你進行了更改，但不想保存，只想快速退出，這個命令會是你的選擇。
:wq: 這個命令表示你想要保存目前的更改，並退出Vim。
ZZ（大寫的zz）: 這是一個快捷命令，功能與:wq相同，但只需要按兩次按鍵。
:x: 這個命令也是保存更改並退出，其功能與:wq和ZZ相似。
學會進入和退出Vim是Vim基礎中的基礎。希望通過今天的分享，你能夠更熟練地使用Vim，並享受它帶來的便利和效率。
-->



---
transition: slide-up
level: 2
layout: default
---

# Vim的模式：掌握Vim的核心
Vim與許多其他文本編輯器的最大不同之處在於它的模式化操作。這些模式使Vim成為一個非常強大的工具。今天，我們將探討Vim的三個主要模式：一般模式、插入模式和命令模式。

|    |     |
|--------------- | --------------- |
|  一般模式 Normal Mode |    |
|  插入模式 Insert Mode |    |
|  命令模式 Command-Line / Ex Mode |    |



<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Vim之所以強大且獨特，很大程度上是因為它的模式化操作。現在，我們就一起來看看這三個主要的模式。

一般模式：
這是Vim的起點。每次你打開Vim，你都會首先進入這個模式。在此模式中，每一個按鍵都不再是單純的輸入字符，它們都有特殊的功能。舉例來說，你可以移動光標、刪除或改變文本。這就像是Vim的指揮中心，大部分的操作都始於此。

插入模式：
當你想要寫下一些文字或者修改已有的內容時，插入模式就派上用場了。按下 i ，你就會進入這個模式，然後你就可以自由地輸入文字了。當你想要回到一般模式，只需按下 Esc 鍵。

命令模式：
在Vim中，有些操作需要更明確的指令，這就是命令模式發揮的場合。想要保存文件？或是替換某段文字？這都需要進入命令模式。只要按下 : ，你就可以在屏幕底部輸入你的命令了。
-->


---
transition: slide-up
level: 2
---

# 光標移動 
 Cursor movement


|  1. 基本光標移動:   | 5. 跳轉至特定行:    |       
| --- | --- | 
|   <kbd>h</kbd> / <kbd>j</kbd> / <kbd>k</kbd> / <kbd>l</kbd> | <kbd>G</kbd> / <kbd>gg</kbd> / <kbd>:&lbrack;number&rbrack; </kbd> |
|  2. 單詞移動: |6. 畫面移動:    |
|   <kbd>w</kbd>  / <kbd>W</kbd>  / <kbd>e</kbd>  / <kbd>E</kbd>  / <kbd>b</kbd>  / <kbd>B</kbd>  |<kbd>ctrl+f</kbd>  / <kbd>ctrl+b</kbd>  / <kbd>ctrl+u</kbd>  / <kbd>ctrl+d</kbd>  / <kbd>zz</kbd>  |
|  3. 行移動:| 7. 匹配括號跳轉:    |
|   <kbd>0</kbd> / <kbd>^</kbd> / <kbd>$</kbd>|<kbd>%</kbd>|
|  4. 段落和區塊移動 |   |
|   <kbd v-pre> <span v-pre>&lbrace;</span> </kbd>  / <kbd> <span v-pre>&rbrace;</span> </kbd>  / <kbd> <span v-pre>&lbrack;</span> </kbd>  / <kbd> <span v-pre> &rbrack; </span> </kbd>| |

<!-- https://sli.dev/guide/animations.html#click-animations -->


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--

[講稿在下面]

1. 基本光標移動:
h: 向左移動一個字符。
j: 向下移動一行。
k: 向上移動一行。
l: 向右移動一個字符。

2. 單詞移動:
w: 移動到下一個單詞的開始。
W: 移動到下一個單詞的開始（考慮標點符號）。
e: 移動到當前單詞的結尾。
E: 移動到當前單詞的結尾（考慮標點符號）。
b: 移動到前一個單詞的開始。
B: 移動到前一個單詞的開始（考慮標點符號）。

3. 行移動:
0: 移動到行首。
^: 移動到當前行的第一個非空白字符。
$: 移動到行尾。
4. 段落和區塊移動:
{: 向上移動到上一個段落的開始。
}: 向下移動到下一個段落的結尾。
[: 向上移動到同一級的上一個區塊。
]: 向下移動到同一級的下一個區塊。

5. 跳轉至特定行:
G: 移動到文件的最後一行。
gg: 移動到文件的第一行。
:[number]: 移動到文件的第[number]行。

6. 畫面移動:
Ctrl + f: 向前滾動一屏。
Ctrl + b: 向後滾動一屏。
Ctrl + u: 向上滾動半屏。
Ctrl + d: 向下滾動半屏。
zz: 將當前行置於畫面中央。

7. 匹配括號跳轉:
%: 跳轉到匹配的括號、中括號或大括號。

[講稿]

今天我要介紹的是Vim中的光標移動。學會這些移動技巧可以大大提高你在Vim中的效率。

首先，我們從基本光標移動開始：

使用 h, j, k, l 你可以在文件中四處移動，就像遊戲中的上下左右按鍵一樣。
接著是單詞移動：

w 和 W 讓你跳至下一個單詞的開始，而 e 和 E 則移動到單詞的結尾。如果想回到前一個單詞，就使用 b 或 B。
針對行移動，我們有：

0 移動至行首，^ 跳到該行的第一個非空白字符，而 $ 則是跳至行尾。
接下來是段落和區塊移動：

使用 { 和 } 可以在段落之間快速跳轉，而 [ 和 ] 則是在區塊間移動。
要快速跳到文件的某一行，你可以使用跳轉至特定行的命令：

G 會跳至文件尾，gg 則跳至文件頭，如果你想跳到特定的行數，例如第10行，只需輸入 :10。
對於畫面移動，我們有以下命令：

Ctrl + f 和 Ctrl + b 分別向前和向後滾動整個畫面；Ctrl + u 和 Ctrl + d 則是滾動半個畫面；而 zz 則是將當前行置於畫面中央。
最後，當你在處理有括號的代碼時，% 允許你在匹配的括號間跳轉。

這就是Vim中的光標移動命令。希望透過今天的分享，你能夠更加熟練地在Vim中移動和編輯。
-->



---
transition: slide-up
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 文字編輯

| 鍵位綁定   | 功能    |
|--------------- | --------------- |
|i	    | 在當前位置之前插入文字   |
|I	    | 在當前行開頭插入文字   |
|a	    | 在當前位置之後插入文字   |
|A	    | 在當前行末尾插入文字   |
|x	    | 刪除光標所在的字符   |
|dd	    | 刪除整行   |
|yy	    | 複製當前行   |
|p	    | 貼上                |


<!--
要向大家介紹的是Vim中的基礎編輯操作。當我們提到編輯，通常會想到插入、刪除和複製貼上等操作。在Vim中，這些操作都有對應的鍵位綁定，讓我們一探究竟。

插入文字：
Vim提供了多種方法來插入文字，讓你可以靈活地在不同位置開始編輯。

i：在當前光標位置之前插入。
I：在當前行的開頭插入。
a：在當前光標位置之後插入。
A：在當前行的末尾插入。
刪除文字：
Vim中刪除操作也很直觀。

x：刪除光標所在的字符。
dd：刪除整行。
複製和貼上：
這是編輯中最常用的操作之一。

yy：複製當前行。
p：將剪貼板中的內容貼到光標後的位置。
這只是Vim中編輯操作的冰山一角，但掌握這些基本操作對於初學者來說已經足夠了。接下來，讓我們透過一個表格再次回顧這些操作。
-->


---
transition: slide-up
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 替換 Substitute
在vim中，替換操作的命令以 :substitute 開頭，通常縮寫為 :s。"substitute" 在英文中意為 "替換"，因此這個命令名稱非常直觀地描述了其功能
substitute 

```bash

:s/old/new/	在當前行替換第一個「old」為「new」
:%s/old/new/g	在整個文檔中替換所有的「old」為「new」
:5s/old/new/	在第5行替換「old」為「new」
:3,8s/old/new/g	在第3到第8行之間替換所有的「old」為「new」
:.,+2s/old/new/g	在當前行及其下兩行中替換所有的「old」為「new」
```

<!--
-->



---
transition: slide-up
layout: cover
background: /public/img/bg-1.jpg
---

# 一般模式命令組合


<!--
今天我要帶領大家進入 Vim 的一般模式，探索如何高效地組合命令來進行編輯。
-->



---
transition: slide-up
layout: default
---

# 命令組合形式


 在正常模式下一個命令的格式是︰

```bash {monaco}
    [number]   command   object     或者     command [number]   object


```


     其意是︰
       number - 代表的是命令執行的次數
       command - 代表要做的事情，比如 d 代表刪除
       object - 代表要操作的對象，比如 w 代表單字/單詞，$ 代表到行末等等。


<!--
在 Vim 的正常模式中，命令的組合和結構是非常核心的概念。當你在 Vim 中工作時，你會發現自己經常需要組合數字、命令和對象來完成特定的操作。

這些組合的基礎格式可以是「[number] command object」或者「command [number] object」。

首先，我們看到的「[number]」部分代表命令執行的次數。舉個例子，「3w」中的「3」告訴 Vim，我們希望命令操作三次。

接著是「command」部分，這代表我們要執行的操作。例如，在「d」命令中，它代表「刪除」。

最後是「object」部分，它表示操作的目標或對象。所以，「w」就代表「單詞」，而「$」則代表「到行尾」。這意味著當你輸入命令「d$」時，你實際上是告訴 Vim「刪除到行尾的所有內容」。

總的來說，Vim 的命令組合結構簡單但功能強大。一旦你熟悉了這些基礎的命令組合和格式，你就可以在 Vim 中進行高效的編輯操作。
-->


---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Code

Use code snippets and get the highlighting directly![^1]

```ts {all|2|1-6|9|all}
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: User) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

<arrow v-click="[3, 4]" x1="400" y1="420" x2="230" y2="330" color="#564" width="3" arrowSize="1" />

[^1]: [Learn More](https://sli.dev/guide/syntax.html#line-highlighting)

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly. And adding your custom components is also super easy.

```html
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/builtin/components.html) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

<!--
Presenter note with **bold**, *italic*, and ~~striked~~ text.

Also, HTML elements are valid:
<div class="flex w-full">
  <span style="flex-grow: 1;">Left content</span>
  <span>Right content</span>
</div>
-->


---
class: px-20
---

# Themes

Slidev comes with powerful theming support. Themes can provide styles, layouts, components, or even configurations for tools. Switching between themes by just **one edit** in your frontmatter:

<div grid="~ cols-2 gap-2" m="-t-2">

```yaml
---
theme: default
---
```

```yaml
---
theme: seriph
---
```

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true" alt="">

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true" alt="">

</div>

Read more about [How to use a theme](https://sli.dev/themes/use.html) and
check out the [Awesome Themes Gallery](https://sli.dev/themes/gallery.html).

---
preload: false
---

# Animations

Animations are powered by [@vueuse/motion](https://motion.vueuse.org/).

```html
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }">
  Slidev
</div>
```

<div class="w-60 relative mt-6">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-square.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-circle.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-triangle.png"
      alt=""
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<!-- vue script setup scripts can be directly used in markdown, and will only affects current page -->
<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<div
  v-motion
  :initial="{ x:35, y: 40, opacity: 0}"
  :enter="{ y: 0, opacity: 1, transition: { delay: 3500 } }">

[Learn More](https://sli.dev/guide/animations.html#motion)

</div>

---

# LaTeX

LaTeX is supported out-of-box powered by [KaTeX](https://katex.org/).

<br>

Inline $\sqrt{3x-1}+(1+x)^2$

Block
$$ {1|3|all}
\begin{array}{c}

\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} &
= \frac{4\pi}{c}\vec{\mathbf{j}}    \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\

\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\

\nabla \cdot \vec{\mathbf{B}} & = 0

\end{array}
$$

<br>

[Learn more](https://sli.dev/guide/syntax#latex)

---

# Diagrams

You can create diagrams / graphs from textual descriptions, directly in your Markdown.

<div class="grid grid-cols-4 gap-5 pt-4 -mb-6">

```mermaid {scale: 0.5, alt: 'A simple sequence diagram'}
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

```mermaid {theme: 'neutral', scale: 0.8}
graph TD
B[Text] --> C{Decision}
C -->|One| D[Result 1]
C -->|Two| E[Result 2]
```

```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectivness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid
```

```plantuml {scale: 0.7}
@startuml

package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}

node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
}

cloud {
  [Example 1]
}


database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}


[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]

@enduml
```

</div>

[Learn More](https://sli.dev/guide/syntax.html#diagrams)

---
src: ./pages/multiple-entries.md
hide: false
---

---
layout: center
class: text-center
---

# Learn More

[Documentations](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/showcases.html)
