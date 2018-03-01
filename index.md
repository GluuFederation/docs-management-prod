# Gluu Documentation Style Guide  

## Introduction
This style guide is intended to make sure that all Gluu documentation is organized, consistent, and legible. It focuses on the editable .md files for optimum formatting on the website. This guide will use the style it is describing, so look at how it is constructed for examples.

## General Text
 - Allow long lines to wrap, rather than manually breaking them. For example, the Introduction paragraph is a single line
 - Keep explanations short and clear
 - Use complete sentences when possible
 - To make text _italicised_, put an `_` on each side, like this: `_word_`
 - To **bold** text, put a double `*` on each end, like this: `**word**`
 - Leave a blank line between paragraphs. Count a header as a paragraph for this purpose
 - Avoid passive voice as much as possible. It's clearer to say that a subject does something than to say a result was done
 
## Lists
 - To make a numbered list, start the line with `1.`
 - To make a bulleted list, start the line with `-`
 - Only use a numbered list if the order of the list matters
 - A line of a list should not end with a period. If it's multiple sentences, like this one, drop the last period
 - Start each item in the list with a capital letter
 

## Headings
 - Headings should be in title format. All important words should be capitalized
 - The main title of the page should start with a single `#`, then each level of subheading should add one. For example, your first subheading should start with `##`, a subheading of that should use `###`, and so on
 
## Links to Other Documents
 - When creating a link to another Gluu document in the same repo, use this format: `[text for the link](./where/the/link/goes.md)`
 - You must link to the `.md` file on GitHub for it to work properly
 - As an example, to make [this link](./example.md) to an example page, you'd type it as `[this link](./example.md)`
 
## Notes and Warnings
Notes and warnings are formatted as follows:

>```
>!!! Note  
>    This is a note. Notice the four spaces before the first word on this line.
>
>!!! Warning  
>    This is a warning. It works just like a note.
>```

It will look like this:

!!! Note  
    This is a note. Notice the four spaces before the first word on this line.
    
!!! Warning  
    This is a warning. It works just like a note.
    
They will not look correct on GitHub, but will convert on the Gluu website.
