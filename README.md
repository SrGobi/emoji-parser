# Emoji Parser
Analizador de emojis para **[Canvacard](https://npmjs.com/package/canvacard)**.

# Emojis
- twemoji
- discord emojis

# Installing

```sh
$ npm i @canvacard/emoji-parser
```

# Example

```js
const Canvas = require("canvas");
const { fillTextWithTwemoji } = require("@canvacard/emoji-parser");
const fs = require("fs");

const canvas = Canvas.createCanvas(500, 270);
const ctx = canvas.getContext("2d");

ctx.fillStyle = "#FFFFFF";
ctx.fillRect(0, 0, canvas.width, canvas.height);

ctx.fillStyle = "#FF0000";
ctx.font = "32px Arial";

fillTextWithTwemoji(ctx, "Hello World 😊 <:kek:750253062689652768>", 120, 150)
    .then(() => {
        fs.writeFileSync("./img.png", canvas.toBuffer())
    })
    .catch(console.error);

```

## Con Typescript

```ts
import { fillTextWithTwemoji } from "@canvacard/emoji-parser";
```

## Preview
![Preview](https://i.imgur.com/1hyyd5P.png)

# Métodos disponibles

## fillTextWithEmoji(context: CanvasRenderingContext2D, text: string, x: number, y: number, options?: DrawTextWithEmojiParams): Promise<void>
Renderiza emojis con `fillType: "fill"`.

## strokeTextWithEmoji(context: CanvasRenderingContext2D, text: string, x: number, y: number, options?: DrawTextWithEmojiParams): Promise<void>
Renderiza emojis con `fillType: "stroke"`.

## drawTextWithEmoji(context: CanvasRenderingContext2D, fillType: "fill" | "stroke", text: string, x: number, y: number, options?: DrawTextWithEmojiParams): Promise<void>
Método principal utilizado por ambos `fillTextWithEmoji` y `strokeTextWithEmoji`.