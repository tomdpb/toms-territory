---
slug: file_auto_organiser
title: "File Auto Organiser"
language: en
author: Tom
Date: 2024-11-10
---

- Status: Complete
- [GitHub project link](https://github.com/tomdpb/File-Auto-organiser)
- Language: Bash/Shell

## About

This is an old project of mine which I completed sometime in January 2021. My Downloads directory is generally quite organised since I usually move files as soon as I download them. Some friends commented on its organisation at the time, but still, wouldn't it be nice if files could just be moved automatically to the correct place?

Enter the [File Auto Organiser](https://github.com/tomdpb/File-Auto-organiser)!

## Functionality

The File Auto Organiser is a simple shell script for organising files in the Dowloads directory, though it isn't necessarily just limited to that directory. The ordered files are then moved to the default Unix directories, but this can easily be changed by modifying the variables at the beginning of the script itself.

## Behind the Scenes

There is no great mystery in this little script. Behind the scenes, the File Auto Organiser detects the file type using the `file` command. This means that changing the extension of the file won't fool the File Auto Organiser. A text file named "not_an_audio.mp3" would be correctly identified as a text file and would then be placed in the Documents directory. Any unidentified file is placed in a newly created unordered directory for it to be manually sorted.
