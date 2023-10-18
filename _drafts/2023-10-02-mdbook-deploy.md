---
layout: post
title: How to build mdBook with Github Actions
date: 2023-09-26 23:11:00 +/-5000
categories: [Environment]
tags: [github, github action, mdbook]     # TAG names should always be lowercase
---


I found two links very useful: 
1. https://github.com/peaceiris/actions-mdbook
2. https://github.com/rust-lang/mdBook/wiki/Automated-Deployment%3A-GitHub-Actions
3. https://katopz.medium.com/how-to-build-mdbook-with-github-actions-eb9899e55d7e
4. https://github.com/rgarrigue/songbook/blob/ad667ec24cf86b04c5a7c98cc8b3e01436925324/.github/workflows/main.yml


I first tried to directly follow the instructions from the third link provided above, it successfully and smoothly lead to success. 
BUT, it does not provide pre-processor of "mdbook katex" https://github.com/lzanini/mdbook-katex which is a pre-processor for building mdbooks with latex equations. 


