# Gluu Documentation Style Guide  

## Introduction
This style guide is intended to make sure that all Gluu documentation is organized, consistent, and legible. It focuses on the editable .md files for optimal formatting on the [Gluu docs website](https://gluu.org/docs). This guide will use the style it is describing, so look at how it is constructed for examples.

## General Text
 - Allow long lines to wrap, rather than manually breaking them. For example, the Introduction paragraph is a single line
 - Keep explanations short and clear
 - Use complete sentences when possible
 - To make text _italicised_, put an `_` on each side, like this: `_word_`
 - To **bold** text, put a double `*` on each end, like this: `**word**`
 - Leave a blank line between paragraphs. Count a header as a paragraph for this purpose
 - Avoid passive voice as much as possible. It's clearer to say that a subject does something than to say a result was done
 - Avoid using `you` in statements as much as possible. For example, instead of saying `You can navigate to...` simply say `Navigate to...` 
 
## Page Setup
 - Start your page with a title on the first line
 - Follow with a concise overview of the document / product's purpose
 - Organize the information in the document from least technical to most technical if possible. Start conceptual, then get detailed
 
## Lists
 - Only use a numbered list if the order of the list matters
 - A line of a list should not end with a period. If it's multiple sentences, like this one, drop the last period
 - Start each item in the list with a capital letter
 - End each item in the list with at least three spaces. This makes sure the line breaks properly
 - To make a *bulleted* list, start each line with `-`
 - To make a *numbered* list, start each line with `1.` For example:
 
 > ```
 > 1. This is the first item
 > 1. This is the second item
 > 1. This is the third item
 > ```
 
 It will look like this:
 1. This is the first item
 1. This is the second item
 1. This is the third item
 
 - To include additional lines in a list item, start the sub-line with four spaces. For example:
 
 ```
1. This is the first item in a list   
    There are four spaces to start this line   
    Another four spaces here   
    This keeps all text inside the numbered list item, before starting...   

1. The following list item   
```
It will look like this:

1. This is the first item in a list   
    There are four spaces to start this line   
    Another four spaces here   
    This keeps all text inside the list, before starting...    

1. The following list item   
 
 - To nest a note inside a list, add four spaces in front of the !!! Note, move to the next line and align the note content with the `N` in the Note. For example:
 ```
     !!! Note
         This is a note that will nest inside a list.
```
 - Nesting a block of code in a numbered list is more challenging, as the list and code block syntaxes clash. It is generally easier to do each line as its own code segment, indented four spaces, with two trailing spaces at the end, like this:

```
1. This is the first item  
    `This is code`  
    `This is also code.`  
1. This is the second item  
```
It will look like this:

1. This is the first item  
    `This is code`  
    `This is also code.`  
1. This is the second item  


## Headings
 - Headings should be in title format. All important words should be capitalized
 - The main title of the page should start with a single `#`, then each level of subheading should add one. For example, the first subheading should start with `##`, a subheading of that should use `###`, and so on
 
## Examples & Navigation
 - When possible, provide an example in the form of code output or a screenshot
 - To instruct a user to click a button, or navigate to a certain page or through a menu, use the following style:

 > ```
 > Navigate to `Configuration` > `Authentication` and click the `Passport` tab
 > ```  
 
 It will look like this:  
 
 Navigate to `Configuration` > `Authentication` and click the `Passport` tab
 
## Linking

### Linking to a Page Within the Same Repo
 - Use this format: `[text for the link](./where/the/link/goes.md)`
 - You must link to the `.md` file on GitHub for it to work properly
 - As an example, to make [this link](./example.md) to an example page, you'd type it as `[this link](./example.md)`
 
### Linking to a Page in a Different Repo
 - You'll need to back out to the closest common path using `/../` to go back a directory
 - For instance, use `[this link](../../../docs-ce-prod/blob/3.1.2/3.1.2/source/installation-guide/install.md)` to get to [this link](../../../docs-ce-prod/blob/3.1.2/3.1.2/source/installation-guide/install.md)
 
### Pictures
 - Displaying a live picture uses the same relative linking syntax as a normal link, except that it leads with an exclamation point
 - For instance, it will look like `![this link](../img/example.png)`
 
 ## Tables
 - Try to make tables visually readable by spacing to make distinct columns
 - The header for each column must be separated by at least three dashes
 - Use outer pipes for consistency
 - If an entry is too long to fit in the neat boxes, that's fine, just try to keep it legible
 - An example table follows:

> ```
> |This    |Is     |A     |Table    |
> |--------|-------|------|---------|
> |1       |2      |3     |4        |
> |Word    |Code   |Text  |Table    |
>```

It looks like this:

|This    |Is     |A     |Table    |
|--------|-------|------|---------|
|1       |2      |3     |4        |
|Word    |Code   |Text  |Table    |

## Notes and Warnings
Notes and warnings are formatted as follows:

```
!!! Note  
    This is a note. Notice the four spaces before the first word on this line.
```
```
!!! Warning  
    This is a warning. It works just like a note.
```

On Github, notes / warning will look like this:

!!! Note
    This is a note. 

!!! Warning
    This is a warning. 

On the Gluu docs site, notes / warnings will look like this:

![notes and warnings](https://user-images.githubusercontent.com/5271048/36987716-a9313876-2062-11e8-98c8-ab65a8bb3299.png)

To nest a note inside a list, add four spaces in front of the !!! Note, move to the next line and align the note content with the `N` in !!! Note. For example:
 ```
     !!! Note
         This is a note that will nest inside a list.
```

## Service Commands 

The Gluu Server supports many different Operating Systems (e.g. RHEL, Debian, Ubuntu, etc.). Service commands can vary. Rather than "hard coding" service commands into documentation, please instead reference the dedicated documentation page for [Service Commands](https://gluu.org/docs/ce/4.0/operation/services/). 

For example, see [this section](https://gluu.org/docs/ce/4.0/admin-guide/attribute/#opendj) of the docs for a production example. 

In documenting a process that involves a service restart, the Service Command documentation is linked:  

```  
 - Add custom attribute 
 - [Restart](https://gluu.org/docs/ce/4.0/operation/services/) the ldap service.
```

The word `Restart` is simply linked to the dedicated doc for Service Commands. 


