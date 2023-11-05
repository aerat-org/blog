+++
title = 'A Simple Workflow'
date = 2023-11-04
draft = false
author = "Kat Nykiel"
+++

## A Simple Workflow

This workflow aims to follow one guiding principle:

> Minimize friction by keeping the technical barrier low

In this end of the spectrum, we aim to use tools most non-technical users would already be familiar with. This sacrifices flexibility that may be available in more dedicated tools, instead aiming for a simpler user experience.

![MS Work publication work](/simple-workflow.png)

## Zotero

Zotero is an open-source reference management tool. It's incredibly useful to organize, read, annotate, and cite academic papers. For a collaborative workflow with Zotero, the simplest approach is to let one author manage the citations in their own library, and implement them in the manuscript using the practices described later in this post.

## Microsoft Word

Like it or not, MS Word is by far the most used writing tool. It has embedded its way into universities and industry alike. MS Word makes it comparatively easy to generate professional-looking documents with minimal configuration, and is well integrated with other Microsoft 365 products.

### Track Changes

MS Word's "Track Changes" feature is incredibly useful in collaborative settings. For collaborators working on the same document, each author can add comments and make their own edits, with all changes saved in a clean markup format.

![Alt text](/track-changes.png)

This feature is invaluable in asynchronous collaboration. It's as easy to use as turning on "Track Changes" under MS Word's "Review" panel.

### Zotero Plugin

MS Word offers many plugins, which greatly extend its functionality. The [Zotero plugin](https://www.zotero.org/support/word_processor_plugin_installation) allows you to insert citations from your Zotero library, and handles much of the formatting for you. For papers with 50+ citations, performance suffers, but this can generally be alleviated by turning off "Automatically update citations."

### Figure References

Within MS Word, you can insert captions and cross-references using Word's "References" panel. This allows you to automatically manage Figure, Table, and Equation references within your document as the content is moved around. While this is more cumbersome than pandoc's cross-ref or LaTeX's \ref{} and \label{}, it replicates the same functionality.

## Cloud Storage Provider

Nearly all organizations have access to some form of shared cloud storage, whether it be Box, Google Drive, OneDrive, or some other system. Many of these offer limited storage for free to small teams. These tools contain limited control systems, that allow you to observe the changes in a document over time and revert to a previous edit if needed. While not as robust as a git-based version control system, this often suffices for collaboration where authors work sequentially rather than in parallel.
