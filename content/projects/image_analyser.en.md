---
slug: image_analyser
title: Image Analyser
language: en
author: Tom
Date: 2024-10-19
---

- Status: Complete
- [_GitHub project link_](https://github.com/tomdpb/Image-Analyser)
- Language: Python

# About

In 2022, I had an issue with some image files on my computer. Somehow, several files ended up being duplicated or triplicated and best of all, some of the duplicates were actually thumbnails or a much lower quality version of the original. Initially I started going through each image one by one, comparing them, and choosing the higher quality image. This was annoying so I came up with an idea: what if a program could do that for me? I searched, but came up with nothing, so I decided I'd program it myself.

The result is a program I simply called Image Analyser which is available on my [GitHub](https://github.com/tomdpb/Image-Analyser).

# Functionality

The funcitonality of the Image Analyser is simple. Simply give it a directory to search in, and it'll return every file name it thinks is identical or similar. There's also an option to enable deletion of the smaller files, but this is disabled by default.

# Behind the Scenes

Behind the scenes, the Image Analyser creates a type of fingerprint for each image using an image hash which is resistant to cropping, although this resistance isn't really needed. These fingerprints/hashes are then compared by taking the hamming difference between them. If the difference is zero or below the threshhold, then we know we've found a similar image. The program then reports similar images to the user, and optionally deletes the image which has fewer pixels.
