# VSCode Nasıl Havalı Yapılır

Ben linuxtayım o sebeple windows specific birşey olduğu zaman pm atın veya yorumda sorun bakayım.

***SONUNA KADAR OKUYUN OKADAR YAZDIM AMK***

## Renk Temam

[Jetbrains New Dark kullanıyorum](https://marketplace.visualstudio.com/items?itemName=MoBalic.jetbrains-new-dark)

## Fontlar

Kullandığım font [Jetbrains Mono'nun nerd font hali](https://www.nerdfonts.com/font-downloads) bulun indirin kurun buradan.


settings.json için değerler (ctrl+shift+p Open User Settings (JSON) tr de ne bilmiyorum)

```json
"editor.fontSize": 13,
"editor.lineHeight": 22,

"editor.fontLigatures": true,
```

[font ligatürleri](https://mirkan.medium.com/yaz%C4%B1-tipi-ba%C4%9Flar%C4%B1-font-ligatures-nedir-cb677c67b47f) olsun güzel gözüküyor.

## Custom CSS injection (yuvarlak havalı şeyler için)

[FriendlyUI](https://marketplace.visualstudio.com/items?itemName=FreeIdom.vscode-friendly-ui) uzantısını kurun

Sonra bi css dosyası oluşturup
içine bunu yerleştirin

```css
* {
  font-family: "JetBrainsMono Nerd Font Mono" !important;
  font-weight: 700 !important;
}

.monaco-editor .squiggly-error{
  border-bottom: 2px solid #FF6464; height: 0.9865rem !important; background: none !important;
}

.monaco-editor .squiggly-info{
  border-bottom: 2px solid #518cc7; height: 0.9865rem !important; background: none !important;
}

.monaco-editor .squiggly-warning{
  border-bottom: 2px solid #F48D3A; height: 0.9865rem !important; background: none !important;
}

.monaco-editor-hover,
.monaco-hover {
  border-radius: 15px !important;
  border-style: solid !important;
  border-color: #333333 !important;
  border-width: 2px !important;
  background-color: transparent !important;
  backdrop-filter: blur(10px) !important;
}

.quick-input-widget {
  border-radius: 15px !important;
  border-style: solid !important;
  border-color: #333333 !important;
  border-width: 2px !important;
  background-color: transparent !important;
  backdrop-filter: blur(10px) !important;
  height: min-content !important;
}

.quick-input-widget *{
  background-color: transparent !important;
}

.quick-input-filter .monaco-inputbox {
  border-radius: 15px !important;
}

.monaco-editor .suggest-widget {
  border-radius: 15px !important;
  border-style: solid !important;
  border-color: #333333 !important;
  border-width: 2px !important;
  background-color: transparent !important;
  backdrop-filter: blur(10px) !important;  
  padding: 5px !important;
}

.monaco-editor .suggest-widget *{
  background-color: transparent !important;
}

.monaco-list-rows {
  background: transparent !important;
}

.monaco-resizable-hover {
  border: none !important;
}
```

Error alt çizgileri düzleşmesin istiyorsanız css dosyasındaki ```.squiggly-``` ile başlayan her şeyi silin

Bunu kafanıza göre değiştirebilirsiniz hatta bir [video](https://www.youtube.com/watch?v=9_I0bySQoCs&t=711s) bırakıyorum buradan nasıl kendi stillerinizi ekleyebileceğinizi de öğrenebilirsiniz.

Ayrıca settings.jsonda olmayan diğer değişiklikleri de gösteriyor kesin izleyin.

sonra friendly ui a dosyanın nerede olduğunu belirtin (settings.jsona bunu koyacaksınız)

```json
"friendly-ui.customCssPath": "C:\\Windowsta\\böyle\\gidin\\dosyaya\\kadar",
```

```json
"friendly-ui.customCssPath": "linuxta/böyle/yapsanız/olur",
```
sonra ctrl+shift+p ile quick input widgeti açın ve enable friendly ui deyin. Her değişiklikten sonra reload friendly ui ile güncelleyebilirsiniz. Linuxtaysanız vscode dosyalarını kendi userınızın kontrolü altına almalısınız (rootaysa olmuyor) atmanız lazım haberiniz olsun

## Terminal

Terminalin fontunu ayrıca değiştirmek zorunda kalabilirsinz

Terminalimin farklı olmasının sebebi [Oh My Posh](https://ohmyposh.dev/) kullanıyorum herhangi bir shell için kullanılabilir. Ama vscode ayarladıktan sonra bakın


## İconlar

[Symbols icon set](https://marketplace.visualstudio.com/items?itemName=miguelsolorio.symbols)

okları kaldırmak istiyorsanız settings.json a bunu ekleyin

```json
"symbols.hidesExplorerArrows": true,
```

## Misc

Quick input widget (ctrl+p) nin yerini sağ üstüne tıklayıp sürükleyerek değiştirebilirsiniz.

Kodun yanındaki minik lambayı kaldırmak için

```json
"editor.lightbulb.enabled": "off",
```

Unicode highlight kaldırmak

```json
"editor.unicodeHighlight.nonBasicASCII": false,
"editor.unicodeHighlight.ambiguousCharacters": false,
"editor.unicodeHighlight.includeComments": false,
```

Workbench'in sağda olması için

```json
"workbench.sideBar.location": "right",
```

Aktif parantez gösterimini kaldırmak için

```json
"editor.guides.highlightActiveBracketPair": false,
"editor.matchBrackets": "never",
"editor.bracketPairColorization.enabled": false,
```

Bunun yerine daha havalısı var nasıl açıklaycağım bilmiyorum böyle

```json
"editor.guides.bracketPairsHorizontal": true,
"editor.guides.highlightActiveIndentation": true,
"editor.guides.bracketPairs": "active",

"workbench.colorCustomizations": {
  "editorBracketPairGuide.activeBackground1": "#FFB86C",
  "editorBracketPairGuide.activeBackground2": "#FF75B5EF",
  "editorBracketPairGuide.activeBackground3": "#45A9F9",
  "editorBracketPairGuide.activeBackground4": "#B084EB",
  "editorBracketPairGuide.activeBackground5": "#E6E6E6",
  "editorBracketPairGuide.activeBackground6": "#19f9d8",
  "editorBracketPairGuide.background1": "#FFB86C",
  "editorBracketPairGuide.background2": "#FF75B5",
  "editorBracketPairGuide.background3": "#45A9F9",
  "editorBracketPairGuide.background4": "#B084EB",
  "editorBracketPairGuide.background5": "#E6E6E6",
  "editorBracketPairGuide.background6": "#19f9d8"
},
```

Minimap kaldırma (sağdaki sinir bozucu şey)

```json
"editor.minimap.enabled": false,
```

Cursorunuz daha kaymak kırpsın istiyorsanız

```json
"editor.cursorBlinking": "smooth",
```

Menu bar kaldırma

```json
"window.menuBarVisibility": "toggle",
```

Native titlebar için

```json
"window.titleBarStyle": "native",
```

Sidebarı sağa almak için

```json
"workbench.sideBar.location": "right",
```

## Uzantı tavsiyeleri

[Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) errörleri güzel gösteriyor.

[GitLess](https://marketplace.visualstudio.com/items?itemName=maattdd.gitless) Git Lens bozmadan önceki versiyon şimdi bazı şeyler için üyelik falan istiyor.

[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense) dosya aratıcısını geze geze path yazmak ile uğraşmamak için çok güzel birşey.

[Strict Whitespace](https://marketplace.visualstudio.com/items?itemName=sidp.strict-whitespace) Whitespaceleri gösteriyor ki silebilelim.

[Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) Yorum satırlarını daha düzenli yapmanızı sağlıyor.

[Dependi](https://marketplace.visualstudio.com/items?itemName=fill-labs.dependi) Çoğu dil için kütüphanelerin güncel olup olmamasını kontrol eden harika bir şey

## Son

Unuttuğum birşey olursa pm atın yardımcı olurum.

Tek isteğim yazılılarım için bol şans dilemeniz :)