# Settings

Add this to your user settings:

```json
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": "keyword.tetris.mino.i",
                "settings": { "foreground": "#53dfc7" }
            },
            {
                "scope": "keyword.tetris.mino.o",
                "settings": { "foreground": "#ffd92e" }
            },
            {
                "scope": "keyword.tetris.mino.t",
                "settings": { "foreground": "#9900FF" }
            },
            {
                "scope": "keyword.tetris.mino.s",
                "settings": { "foreground": "#5fce5f" }
            },
            {
                "scope": "keyword.tetris.mino.z",
                "settings": { "foreground": "#cf4d4d" }
            },
            {
                "scope": "keyword.tetris.mino.j",
                "settings": { "foreground": "#5858cf" }
            },
            {
                "scope": "keyword.tetris.mino.l",
                "settings": { "foreground": "#e0824b" }
            },
            {
                "scope": "keyword.tetris.mino.garbage",
                "settings": { "foreground": "#a1a1a1" }
            },
            {
                "scope": "keyword.tetris.mino.unclearable",
                "settings": { "foreground": "#555555" }
            }
        ]
    }
```

# Example Code

Example code with template function:

```ts
/** Clean up a tetris template string and return an array of lines **/
function tetris(str: TemplateStringsArray): string[] {
    return str
        .join("") // TODO: deal with templates
        .replace(/^\n|\n$/g, "") // Remove leading and trailing newlines
        .split("\n") // Split back on newlines
        .map(s => s.padEnd(10, " ").substring(0, 10)); // Make all lines 10 chars
}

const dtCannon = tetris`
  LL      
   L      
JJ LT#####
J  TTTI###
J   SSIZZ#
OO SSLIJZZ
OO LLLIJJJ
`;

console.log(JSON.stringify(dtCannon));
```