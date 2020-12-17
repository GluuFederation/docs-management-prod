# Gluu Documentation Guide  

## Introduction
This guide is intended to make sure that all Gluu documentation is organized, consistent, and legible. The guide covers the general architecture of the docs and the best practices for the editable .md files for optimal formatting on the [Gluu docs website](https://gluu.org/docs). This guide will use the style it is describing, so look at how it is constructed for examples.

## Configuration

### Overview

Our documentation is built using [Mkdocs](https://www.mkdocs.org/) with the [Material](https://squidfunk.github.io/mkdocs-material/) theme. The next section will present a working configuration file (mkdocs.yml) from our main Gluu Server documentation.

### Sample mkdocs.yml

As an example of how our configuration is structured, the following section breaks down the `mkdocs.yml` file for the [Gluu Server version 4.2 docs](https://github.com/GluuFederation/docs-gluu-server-prod/blob/4.2/docs/mkdocs.yml).

The first section provides the basic information for the documentation pages. 

- `site-name`: the name shown in a tab open to any page on the documentation, as well as the top of the navigation bar  
- `site-description`: the description that comes up when a link is posted to the docs  
- `copyright`: the copyright text at the bottom of each page  

```
# Project information
site_name: Gluu Server 4.2 Docs
site_description: Documentation for Gluu Server

# Copyright
copyright: Copyright &copy; 2020, Gluu, Inc.
```

The following section lists details about the Github repository where the doc source pages are found. 

- `docs_dir`: The name of the directory containing all files to be generated into the docs website. We use `source` by default. This directory must be in the same directory as the `mkdocs.yml` file.
- `repo_name`: The name (not URL) of the repo. Mkdocs uses this field to pull the Forks and Stars from GitHub to display on each page.
- `repo_url`: The base URL for the repo.
- `edit_uri`: The rest of the URL for the edit button on each page. It appends to the `repo_url` field.

```
# Repository
docs_dir: source
repo_name: GluuFederation/docs-gluu-server-prod
repo_url: https://github.com/GluuFederation/docs-gluu-server-prod/
edit_uri: edit/4.2/docs/source
```

This section details specific configuration options for the documentation pages. 

- `theme`
  - `name`: Sets the theme used by Mkdocs. This can either be one included in Mkdocs by default, such as the `mkdocs` theme, or a custom one. We have installed Material separately into our installation.
  - `custom_dir`: Like `docs_dir` in the previous section, this sets a directory for custom theme override pages. Create a file in this directory with exactly the same path as a theme page and it will overwrite that page for this branch specifically. This is useful for single-page documentation branches to remove the navigation bar and other customizations.
  - `palette`: Color options for the theme
  - `logo`: The filename for the organization logo for the header. Must be located in the `img` directory inside `docs_dir`.
  - `favicon`: The filename for the favicon on the tab. Must be located in the `img` directory inside `docs_dir`.
  - `extra`: Extra information to be included in the metadata
  - `extra_css`: The filepath to any custom CSS, relative to `docs_dir`. The `tabs.css` sheet is needed for the Tabbed extension

```
# Configuration
theme:
    name: material
    custom_dir: 'theme'
    palette:
        primary: 'green'
        accent: 'green'
    logo: 'gluu.jpg'
    favicon: 'favicon.ico'
extra:
    version: '4.2'
extra_css:
  - css/tabs.css
```

This section sets the Google tracking information for the specific docs branch. This information is the same in all repos.

```
# Tracking
google_analytics:
  - 'UA-31008645-7'
  - 'auto'
```

This section configures specific extensions. The extensions with no prefix are standard [Mkdocs extensions](https://python-markdown.github.io/extensions/), the extensions with `pymdownx.` prefixes are [PyMdown extensions](https://facelessuser.github.io/pymdown-extensions/)

```
# Extensions
markdown_extensions:
- admonition
- attr_list
- toc:
     permalink: '#'
- codehilite
- pymdownx.superfences
- pymdownx.tabbed
```

This is the actual content of the documentation files. The files listed after the `nav:` tag will appear in the table of contents in exactly this format. The string before each `:` is the name that will appear in the TOC and as a title on tabs, the string after is the path to each .md file relative to `docs_dir`.

```
# Navigation
nav:
- 'Versions':
    - '4.2': 'https://gluu.org/docs/gluu-server/4.2/'
#    - '5.0': 'https://gluu.org/docs/gluu-server/5.0/'
    - '4.1': 'https://gluu.org/docs/gluu-server/4.1/'
    - '4.0': 'https://gluu.org/docs/gluu-server/4.0/'
    - 'EOL Versions': 'https://gluu.org/docs/eol/'
- ' ': 'https://gluu.org/docs'
- ' ': 'https://gluu.org/docs'
- Home: 'index.md'
- Release Notes: 'release-notes/index.md'
- Whats new in v4: '4.x-intro.md'
- Installation Guide:
        - 'VM Preparation': 'installation-guide/index.md'
        - 'Installation':
#            - 'Start here': 'installation-guide/install.md'
#            - 'Test Drive': 'installation-guide/test-drive.md'
            - 'Kubernetes': 'installation-guide/install-kubernetes.md'
            - 'Docker': 'installation-guide/install-docker.md'
            - 'Ubuntu': 'installation-guide/install-ubuntu.md'
            - 'Debian': 'installation-guide/install-debian.md'
            - 'RHEL': 'installation-guide/install-rhel.md'
            - 'CentOS': 'installation-guide/install-centos.md'
        - 'Setup Script Options': 'installation-guide/setup_py.md'
        - 'Upgrade to 4.2': 'upgrade/index.md'
        - 'Clustering': 'installation-guide/cluster.md'
```

## Style Guide

### General Text
 - Allow long lines to wrap, rather than manually breaking them. For example, the Introduction paragraph is a single line
 - Keep explanations short and clear
 - Use complete sentences when possible
 - To make text _italicised_, put an `_` on each side, like this: `_word_`
 - To **bold** text, put a double `*` on each end, like this: `**word**`
 - Leave a blank line between paragraphs. Count a header as a paragraph for this purpose
 - Avoid passive voice as much as possible. It's clearer to say that a subject does something than to say a result was done
 - Avoid using `you` in statements as much as possible. For example, instead of saying `You can navigate to...` simply say `Navigate to...` 
 
### Page Setup
 - Start your page with a title on the first line
 - Follow with a concise overview of the document / product's purpose
 - Organize the information in the document from least technical to most technical if possible. Start conceptual, then get detailed
 
### Lists
 - Only use a numbered list if the order of the list matters
 - A line of a list should not end with a period. If it's multiple sentences, like this one, drop the last period
 - Start each item in the list with a capital letter
 - End each item in the list with at least three spaces. This makes sure the line breaks properly
 - To make a *bulleted* list, start each line with `-`
 - To make a *numbered* list, start each line with `1.` For example:
 
    ```
    1. This is the first item
    1. This is the second item
    1. This is the third item
    ```
 
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

#### Other formatting considerations

 - [Admonitions](#admonitions) cannot be nested inside a list. They must be aligned all the way left. Inserting them within a list will break the list sequence (starting back over from 1).
    
 - Nesting a [fenced block of code](#code-formatting) in a numbered list is more challenging, as the list and code block syntaxes clash. To nest a code block into a list, insert four spaces to the left of all lines of the formatting. For example:

```
1. This is the first item  
    ```
    This is code  
    This is also code.
    ```
1. This is the second item  
```

It will look like this:

1. This is the first item  
    ```
    This is code  
    This is also code.
    ```
1. This is the second item  


### Headings
 - Headings should be in title format. All important words should be capitalized
 - The main title of the page should start with a single `#`, then each level of subheading should add one. For example, the first subheading should start with `##`, a subheading of that should use `###`, and so on

### Code Formatting
  - To format text as code within a line of normal text, surround the code with a single backtick (\`).
  - If the code is to be on its own line, it should be a fenced code block. To make a fenced code block, make a line before and after the code with three backticks:
  
    ```
        ```
        This is code
        ```
    ```
    
  - We use the [SuperFences](https://facelessuser.github.io/pymdown-extensions/extensions/superfences/) plugin to enhance this functionality.
  
  
### Examples & Navigation
 - When possible, provide an example in the form of code output or a screenshot
 - To instruct a user to click a button, or navigate to a certain page or through a menu, use the following style:

     ```
     Navigate to `Configuration` > `Authentication` and click the `Passport` tab
     ```  
 
It will look like this:  
 
Navigate to `Configuration` > `Authentication` and click the `Passport` tab
 
### Linking

#### Linking to a page within the same repo
 - Use this format: `[text for the link](./where/the/link/goes.md)`
 - You must link to the `.md` file on GitHub for it to work properly
 - As an example, to make [this link](./example.md) to an example page, you'd type it as `[this link](./example.md)`
 
#### Linking to an external page in a Different Repo
 - Link to the rendered documentation page (on https://gluu.org/docs/*)
 - For instance, use `[this link](https://www.gluu.org/docs/ce/installation-guide/install/)` to get to [this link](https://www.gluu.org/docs/ce/installation-guide/install/)
 
#### Pictures
 - Displaying a live picture uses the same relative linking syntax as a normal link, except that it leads with an exclamation point
 - For instance, it will look like `![this link](../img/example.png)`
 
#### Service Commands 

The Gluu Server supports many different Operating Systems (e.g. RHEL, Debian, Ubuntu, etc.). Service commands can vary. Rather than "hard coding" service commands into documentation, please instead reference the dedicated documentation page for [Service Commands](https://gluu.org/docs/ce/4.0/operation/services/). 

For example, see [this section](https://gluu.org/docs/ce/4.0/admin-guide/attribute/#opendj) of the docs for a production example. 

In documenting a process that involves a service restart, the Service Command documentation is linked:  

```  
## Add the attribute to LDAP

 - Add custom attribute 
 - [Restart](https://gluu.org/docs/ce/4.0/operation/services/) the ldap service.
```

The word `Restart` is simply linked to the dedicated doc for Service Commands. 
 
### Tables
 - Try to make tables visually readable by spacing to make distinct columns
 - The header for each column must be separated by at least three dashes
 - Use outer pipes for consistency
 - If an entry is too long to fit in the neat boxes, that's fine, just try to keep it legible
 - An example table follows:

 ```
 |This    |Is     |A     |Table    |
 |--------|-------|------|---------|
 |1       |2      |3     |4        |
 |Word    |Code   |Text  |Table    |
```

It looks like this:

|This    |Is     |A     |Table    |
|--------|-------|------|---------|
|1       |2      |3     |4        |
|Word    |Code   |Text  |Table    |
