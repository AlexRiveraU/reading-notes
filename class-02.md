# CLASS-02

>ADDING MARKUP TEXT

* **Structural markup:** Elements to describe headings and paragraphs.
* **Semantic markup:** Provides extra information, like where emphasis should be placed in a sentence, quote references, meaning of acronyms, etc.

STRUCTURAL TEXT TAGS

1. HEADINGS: There are six levels \<h1> \<h2> \<h3> \<h4> \<h5> \<h6>
2. PARAGRAPHS: \<p>
3. BOLD & ITALIC: \<b> & \<i>
4. SUPERSCRIPT & SUBSCRIPT: \<sup> & \<sub>
5. LINE BREAKS & HORIZONTAL RULES: These two are empty elements. \<br /> & \<hr />

SEMANTIC TEXT TAGS

1. STRONG & EMPHASIS: \<strong> & \<em>
2. QUOTATIONS: \<blockquote> & \<q>
3. ABBREVIATIONS & ACRONYMS: \<abbr>
4. CITATIONS & DEFINITIONS: \<cite> & \<dfn>
5. AUTHOR DETAILS: \<address>
6. CHANGES TO CONTENT: \<ins> \<del> & \<s>

---

## INTRODUCTION TO CSS

CSS Allows us to create rules that specify how the content of an element should appear on a page. The style of a website. It works by associating rules with HTML elements that specify how the content of elements should be displayed.

>CSS Rules:

1. SELECTOR: Indicates which element the rules applies to.
2. DECLARATIONS: Indicates how the element referred to in the selector should be styled. They are split in two parts:
   * ***Property:*** Indicates the aspects of the element you want to change.
   * ***Value:*** Specify the settings you want to use for the chosen properties.

        p {
          font- family: Arial;
          color: blue;
          }

> CSS External & Internal

* EXTERNAL: We use html tag \<link> to tell the browser where to find the CSS file. (e.g)

    \<link href="css/styles.css" type:"text/css" rel:"stylesheet" />

* INTERNAL: We use html tag \<style> to add css within the html file.

> CSS Cascade

If there are many rules that apply to an element, that last rule will take precedence. If one selector is more specific, that one will rule instead.

---

## BASIC JAVASCRIPT INSTRUCTIONS

JavaScript is a series of instructions that a computer can follow one by one to obtain a particular result. JavaScript is case sensitive.

* STATEMENTS: Each individual instruction that a computer should follow. (e.g)
* CODE BLOCK: Contents of code inside { } Each code block can contain many statements.
Variables: Store pieces of information temporarily that are used in the script.

### VARIABLES

What the script uses to temporarily store the pieces of information it needs to do its job.

* **DECLARING:** Variables need to be created and given a name before being used, this is known as declaring a variable.
* **ASSIGNING VALUE:** Once created, you can tell it what information you would it like to store. You would be assigning a value to a variable.

>TYPES OF VARIABLES

* Numbers: (0-9)
* Strings: Text, letters and other characters
* Boolean: True or False
* Arrays: Store a list of values

**EXPRESSIONS:** Evaluate into a single value. There are two types:

1. Expressions that just assign a value to a variable.
2. Expressions that use two or more values to return a single value.

**OPERATORS:** Expressions rely on operators to create a single value from one or more values.

* Assignment Operators: Assign a value to a variable
* Arithmetic Operators: Performs basic Math
* String Operators: Combine two strings
* Comparison Operators: Compares two values and return true or false
* Logical Operators: Combine expressions and return true or false

>EVALUATING CONDITIONS & CONDITIONAL STATEMENTS

There are two components to a decision:

1. An expression is evaluated and returns a value.
2. A conditional statement says what to do in a given situation.

if (score < 50) {
  document.write('You passed!');
} else {
    document.write('Try again...')
}

### Things I want to know more about

* Using comparison and logical operators.

---

[-back](https://alexriverau.github.io/reading-notes/)