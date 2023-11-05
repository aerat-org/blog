+++
title = 'A Robust Workflow'
date = 2023-11-05
draft = false
author = "Aerith Netzer"
+++

![Robust Workflow](/Collaborative_Workflow_Arch.png)

Scholarship is a collaborative and iterative process, where small changes build up over time to create a final product. Further, we should strive to make our research process as open and transparent as possible. The workflow I propose as a solution to these problems is a workflow that prioritizes open source tools, version control, and reproducibility.  

This article describes a collaborative scholarly workflow for digital-first publishing. There are several elements of this workflow, below is a list of how they fit together.

- File Format: Markdown
- Version Control: Git
- Hosting: GitHub
- Citation Management: Zotero
- Text Editor: VS Code
- Conversion: Pandoc

## "Quick" Start

### Software Downloads

1. Zotero
   1. Better BibTex - Zotero plugin that allows for better citation management
2. VSCode
   1. Pandoc Citer - VSCode Extension that will allow us to cite in Markdown easily
   2. Pandoc Render - VSCode extension that allows for a reproducible pandoc rendering command, will allow for a faster way to render documents

#### Creating a new project

1. Create a new repository on GitHub
2. Clone the empty repository to your local machine
3. Create a folder for each author on the project such that the folder structure looks like this:

```
project
├── author1
│   ├── author1_content.md
├── author2
│   ├── author2_content.md
```

#### Autoexporting .bib file

1. Create a .bib file in the root directory of your project
2. Configure Better BibTex to export to this .bib file
3. Enable automatic export

Now you can add citations from the zotero browser plugin, and they will automatically be added to your .bib file.

Now, if you are author1, your folder structure should look like this:

```
project
├── author1
│   ├── author1_content.md
│   ├── author1.bib
├── author2
│   ├── author2_content.md
```

Author2 will set up their own sources on their own machine, and will have their own .bib file.

#### Setting up VSCode

Now, we want to start writing, to do this, open VSCode.

1. Open the project folder in VSCode
2. Open the pandoc citer settings, and have the .bib file point to wherever your .bib file is stored.

#### Setting up Zotero and Better Bibtex

Follow the instructions for installing Better Bibtex here: [Link](https://retorque.re/zotero-better-bibtex/installation/)

Follow the instructions for configuring Better Bibtex here: [Link](https://retorque.re/zotero-better-bibtex/configuration/)

Open the pandoc citer settings, and have the .bib file point to wherever your .bib file is stored.

![Pandoc Citer Settings](/pandoc_citer.png)

Now, when you type `@` in a markdown file, you should see a list of your citations.

#### Setting up Pandoc Render

Pandoc-render makes a reproducible pandoc command, which will allow you to render your document from the VS Code terminal. You don't have to use the command line to render your document now!

##### A Note on CSL files

CSL files are citation style language files, which tell pandoc how to format your citations. You can find a list of CSL files here: 

Follow the instructions for installing vscode-pandoc here: [Link](https://marketplace.visualstudio.com/items?itemName=DougFinke.vscode-pandoc)

Open the vscode-pandoc settings, and set the pdf output command to something like the following: 

```
--csl=<path/to/your/csl/file.csl> --metadata link-citations=true --filter mermaid-filter --filter pandoc-crossref --citeproc --standalone --from=markdown+yaml_metadata_block
```

Let's break down what this command does:

- `--csl=<path/to/your/csl/file.csl>`: This tells pandoc where to find your CSL file, which will tell pandoc how to format your citations
- `--metadata link-citations=true`: This tells pandoc to link your citations to the bibliography
- `--filter mermaid-filter`: This tells pandoc to render mermaid diagrams
- `--filter pandoc-crossref`: This tells pandoc to render cross references
- `--citeproc`: This tells pandoc to use the citation processor
- `--standalone`: This tells pandoc to render a standalone document
- `--from=markdown+yaml_metadata_block`: This tells pandoc to render from markdown, and to use the yaml metadata block

You can also use this command for all the other output formats, but I tend to only use PDF and sometimes DOCX if I am working with someone who is not familiar with Markdown.

Now, when you type `ctrl+shift+p` and type `pandoc`, you should see a list of commands, including `pandoc render`, which will then show a list of output formats. Select the PDF, and it will render your document.

#### Let's Start Writing!

You can now start writing your document, you can use VSCode to write your essay/article/book/dissertation, use bibtex keys to cite sources, and then render your document to PDF, all while using git to track changes and collaborate with others.