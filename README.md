# babel-plugin-html-tag

Statically evaluates and minifies tagged `` html`<..>` `` template literals into strings

## What it does:

Minifies tagged template literals (by default using `html` tag) via `html-minifier` then removes the tag:

In:

```js
const a = html`<p class="zoom center justify">
    This is paragraph with ${b} subsitutions 
    at several lines: ${1 + 2}
</p>`;

const z = html`<table class="center">
    <tr class='left'>
        <td>HTML without substitutions</td>
    </tr>
</table>`;
```

Out:

```js
const a = `<p class="zoom center justify">This is paragraph with ${b} subsitutions at several lines: ${1 +
  2}</p>`;

// becomes static one line string if there is no substitutions
const z =
  '<table class="center"><tr class="left"><td>HTML without substitutions</td></tr></table>';
```

### Tip

Try it with Visual Studio Code [bierner.lit-html](https://marketplace.visualstudio.com/items?itemName=bierner.lit-html) plugin for beautiful syntax highlight and HTML autocomplete inside tagged HTML string.

## Credits

Inspired by [babel-plugin-template-html-minifier](https://github.com/goto-bus-stop/babel-plugin-template-html-minifier) and [babel-plugin-graphql-tag](https://github.com/gajus/babel-plugin-graphql-tag)
