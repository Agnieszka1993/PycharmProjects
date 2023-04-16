# HTML formatter

## Story

You work with the military as part of a web developer team
responsible for creating various web applications for internal use. Your boss,
Major Issue thinks that an [HTML formatter](https://htmlformatter.com/) would
boost team performance, however, he doesn't want you to use any 3rd party
applications, because you are working with confidential data and imported code
is considered to be a security risk for the army.

Your job is to develop a simple HTML/JavaScript page that can do the trick.

The result must function similar to the following example.

![HTML formatter solution animgif](media/web/html-formatter-solution.gif)

## What are you going to learn?

- Manipulate the DOM using JavaScript.
- Use regular expressions.
- Understand the stack data structure.
- Develop algorithmic thinking.

## Tasks

1. Implement the indentation feature: after clicking the `Format` button, the HTML code written in the `#source` textarea must appear in the `#target` div with proper indentation.
    - Clicking the `Format` button copies all the text from the textarea on the left side to the target div on the right side.
    - Attributes on valid HTML elements are kept, for example, `<link rel="stylesheet" type="text/css" href="theme.css">`.
    - Every opening (or single) tag appears in a new line. The text content of the element (the raw text between the tags) are displayed right after the opening tag (such as `<p>Lorem ipsum dolor...`).
    - Every child tag is indented with four more spaces than its parent tag.
    - Closing tags appear in-line with the opening tags, if
the element has no children elements, only textual content, for example,
`<p>Lorem ipsum</p>`.
    - When the element has children elements,
the closing tag appears in a new line, such as `/ul` and `/p` in the following example.
```
<ul>
    <li>One</li>
    <li>One</li>
</ul>```
or
```
<p>Lorem ipsum
    <em>dolor</em>
    <em>sit amet</em>
</p>```
    - When the element has textual content _after_ a child element,
the text is displayed on the same level as the children,
and the parent closing tag appears in a new line.
```
<p>Lorem ipsum
    <em>dolor</em>
    sit amet !!!
</p>```
    - There is no extra whitespace between tags and text nodes (that is, **no** code looks like this: `<h1>text node         </h1>`).
    - There are no extra whitespaces between rows.

2. Implement the validity checker feature: the program must show an error if invalid or unknown tags are found in the source code.
    - Only the following tags are allowed in the code: `html`, `head`, `meta`, `title`, `script`, `link`, `body`, `div`, `p`, `h1`, `h2`, `h3`, `h4`, `h5`, `h6`, `ul`, `ol`, `li`, `a`, `br`, `strong`, `em`, `span`, `code`, `table`, `tr`, `td`, `form`, `button`, `input`, `option`, `select`, `textarea`
    - If there is an invalid tag in the source code, clicking the `Format` button results in the following error message displayed in the target div: `Not valid HTML! Unknown tag: <invalid tag name>` where the actual invalid tag name is shown.

3. Improve the validity checker feature further: the program must show an error if regular (paired) tags are not properly nested (that is, opening or closing tags are missing, or the closing order is wrong, similar to the following example: `<h1><p></h1></p>`).
    - Only properly nested regular (paired) tags are allowed.
    - If there are orphaned regular tags or invalid nesting in the source code, clicking the `Format` button results in the following error message displayed in the target div: `Not valid HTML! No pair for <orphaned tag>!`.

4. Implement separate colors for separate HTML roles: tags must be green, attribute keys blue, attribute values red, and textual content black.
    - Every tag along with the angle brackets (`<>`) and the slash (`/`) appears in green in the target div.
    - Every attribute along with the equal sign (`=`) appears in blue in the target div.
    - Every attribute value along with the quotation marks (`""`) appears in red in the target div.
    - Every text node appears in black in the target div.

5. Implement the tag highlighting feature: moving the mouse over a tag must highlight also its distant parts.
    - When moving the mouse over on a tag part (angle brackets, slash, or name) in the target div on the right side, all tag parts are highlighted.
    - When moving the mouse over on an attribute part (key or value), no highlight appears.
    - When moving the mouse over on a tag part (angle brackets, slash, or name) in the target div on the right side, a pair tag is highlighted (if there is one), for example, hovering over `</div>` highlights the corresponding `<div>`.

## General requirements

None

## Hints

- Use the contents of `test.html` for testing your program.
- Use a JavaScript array as a _stack_ (using its `push` and `pop` methods only)
  for keeping track of tag pairs.
- Use the JavaScript `matchAll` function with regular expressions to match tags,
  attributes and values.
    - Use a regular expression tester site to test and improve your regular expression.
- Make sure that you understand at least the following concepts when it comes to regular expressions.
    - regex patterns,
    - regex options or flags,
    - greedy / lazy matching,
    - capturing groups.
- You may face problems when creating event handler functions for dynamically
  created elements. Try reading about scopes and closures in this context.

## Background materials

- <i class="far fa-exclamation"></i> [Anatomy of an HTML element](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- <i class="far fa-exclamation"></i> [About the stack data structure](project/curriculum/materials/competencies/data-structures-basics/stack.md.html)
- <i class="far fa-exclamation"></i> [DOM manipulation](project/curriculum/materials/pages/javascript/javascript-dom.md)
- <i class="far fa-exclamation"></i> [About regular expressions](https://developer.mozilla.org/en/docs/Web/JavaScript/Guide/Regular_Expressions)
- <i class="far fa-book-open"></i> [Regular expression tutorial](https://regexone.com/)
- <i class="far fa-book-open"></i> [Regular expression tester site](https://regex101.com/)
- <i class="far fa-book-open"></i> [About adding dynamical element with event listeners](https://itnext.io/javascript-event-listeners-delegation-vs-closures-8fe52ac49872)
