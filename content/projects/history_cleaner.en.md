---
slug: history_file_cleaner
title: "History File Cleaner"
language: en
author: Tom
Date: 2024-11-20
---

- Status: Complete
- [GitHub project link](https://github.com/tomdpb/history_file_cleaner)
- Language: Go

## About

When I first started tinkering around with the Linux terminal, like everyone, I knew no commands, and having the command history automatically saved in a file was very useful. As time went on, I became more familiar with the terminal and its commands, to the point where some commands felt like second nature. Eventually, I didn't want every command to be saved to the history file and mostly wanted to save commands that I would use occasionally, but by the next time I had to use them, I would forget what they were. This ended up morphing into somewhat of a bad habit: as many terminal users will know, if the leading character is an empty space, the command will not be saved to the history file (assuming this behaviour is set). I became so used to writing an extra space before my commands, that now I add a space automatically even when I didn't intend to do so.

Enter the [history file cleaner](https://github.com/tomdpb/history_file_cleaner)! Now, by setting some regular expression patterns I don't want saved to my history file, I can re-train myself to not include a leading space. All I have to do is run the simple program, and any lines in my history file which match the regular expression are automatically removed!

"But Tom, won't that mean now you need to remember to run your little program instead?"

Well, kind of. I just set a _cronjob_ to run the program once a day, so I don't have to think about it at all. As long as _cron_ is working, I don't need to think about the program at all, and I can safely not include a leading space in my commands.

## Functionality

The [history file cleaner](https://github.com/tomdpb/history_file_cleaner) has one goal: remove lines in a history file that match regular expressions given in another file. Although the program is intended to work with history files, any file can be passed as an argument to the program. The used regex patterns are set in the `regex_patterns.txt` file which should be passed to the binary (which must be compiled by the user) with the `--regexFile` flag.

Be aware that the regex is very strict!

## Behind the Scenes

Behind the scenes, the [history file cleaner](https://github.com/tomdpb/history_file_cleaner) reads the `regex_patterns.txt` file and adds them all to a slice. The program then creates a backup of the file it received as an argument, and compares each line with the regex patters. If any lines match, the line is skipped, otherwise the line is added to a new file. Once all lines have been checked, the newly created file replaces the original file that the program received as an argument.
