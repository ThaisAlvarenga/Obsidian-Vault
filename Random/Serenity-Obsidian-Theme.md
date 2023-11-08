Para referencias sobre como usar Page Gallery, [revisa el Github](https://github.com/tokenshift/obsidian-page-gallery/tree/main)

# 💭 Checkbox States

- [/] incomplete
- [-] cancelled
- [>] forwarded
- [<] scheduling
- [?] question
- [!] important
- [*] star
- [“] quote
- [l] location
- [b] bookmark
- [i] information
- [S] savings
- [I] idea
- [p] pros
- [c] cons
- [f] fire
- [k] key
- [w] win
- [u] up
- [d] down 
Syntax is the same as that of the Minimal theme.

```markdown
- [/] incomplete
- [-]  cancelled
- [>] forwarded
- [<] scheduling
- [?] question
- [!] important
- [*] star
- [“] quote
- [l] location
- [b] bookmark
- [i] information
- [S] savings
- [I] idea
- [p] pros
- [c]  cons
- [f] fire
- [k] key
- [w] win
- [u] up
- [d] down 
```

Plus some additional checkboxes.

- [@] person/user
- [B] beat
- [s] save (download)
- [a] link 
- [L] like
- [e] event
- [g] game
- [h] home
- [H] help 
- [j] junk
- [m] memo
- [n] next
- [N] navigation 
- [o] open
- [q] quick
- [r] report
- [t]  tip
- [+] add
- [v] visibility

```
- [@] person/user
- [B] beat
- [s] save (download)
- [a] link 
- [L] like
- [e] event
- [g] game
- [h] home
- [H] help 
- [j] junk
- [m] memo
- [n] next
- [N] navigation 
- [o] open
- [q] quick
- [r] report
- [t]  tip
- [+] add
- [v] visibility
```

#### Speech Bubbles

![](https://raw.githubusercontent.com/Bluemoondragon07/Obsidian-Serenity/HEAD/speech-bubbles.png)

##### Syntax

Syntax for individual speech bubbles is the same as that of the AnuPpuccin theme.

- [0] Speech Bubble 1
- [1] Speech Bubble 2
- [2] Speech Bubble 3
- [3] Speech Bubble 4
- [4] Speech Bubble 5
- [5] Speech Bubble 6
- [6] Speech Bubble 7
- [7] Speech Bubble 8
- [8] Speech Bubble 9
- [9] Speech Bubble 10

```
- [0] Speech Bubble 1
- [1] Speech Bubble 2
- [2] Speech Bubble 3
- [3] Speech Bubble 4
- [4] Speech Bubble 5
- [5] Speech Bubble 6
- [6] Speech Bubble 7
- [7] Speech Bubble 8
- [8] Speech Bubble 9
- [9] Speech Bubble 10
```

###### Inside a speech bubble

The first **bold** text in a speech bubble will have its own line and will be treated like a title.

- [0] **Jim** Hi, I'm Jim.

```
- [0] **Jim** Hi, I'm Jim.
```

This will have **Jim** show up as speech bubble title.  
Images on the same line as the speech bubble are also supported.

#### Custom Callouts

> Keywords are the same as those for the checklists.  
> For example, the _cancelled_ callout is `>[!cancelled]` or `>[!-]`.

> [!/] incomplete
> My task

> [!-] cancelled
> My first trip 

> [!>] forwarded

> [!<] scheduling

> [!?] question

>[!!] important

>[!*] star

>[!“] quote

>[!l] location

> [!b] bookmark

>[!i] information

>[!S] savings
>So much money inshAllah

>[!I] idea

>[!p] pros

>[!c] cons

>[!f] fire

>[!k] key

>[!w] win

>[!u] up

>[!d] down 


### Custom HTML Attributes

#### `data-comment`

Initiate a custom "comment" tooltip on hover.

###### Example

<span data-comment="This is a comment">I will show a tooltip on hover!</span>
`<span data-comment="This is a comment">I will show a tooltip on hover!</span>`

#### `data-above`

Show 'annotations' above the text on hover.

###### Example

<span data-above="I'm an annotation above the text!">I have annotations on hover!</span>
`<span data-above="I'm an annotation above the text!">I have annotations on hover!</span>`

#### Extra Attribute Styling

<abbr title="This shows on hover">text</abbr>
The abbreviation element (`<abbr title="This shows on hover">text</abbr>`) has some extra styling applied to it to make it stand out more.
