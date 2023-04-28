### Justy Sez:  I've forked this to try and fix a bug that is preventing me from using this extension as advetised.

The problem:  After the initial build task, main.vs is created correctly and has expected debug symbols.  However, immediately after choosing the Vice emulator (x64xc) this file is empty (or emptied, more to the point).  The file is still there, but it is empty.  The reported error is:

[error] [Extension Host] stderr: Argument 'main.vs' not valid for option `-moncommands'.
Error parsing command-line options, bailing out. For help use '-help'

My best guess is that it is this now empty main.vs file that is throwing this error.

Additionaly, curiously, there is a line of code in the extension that seems to create the .vs from the .prg file, which doesn't seem right.

This repo is apparently ahead of the MS Extension Marketplace, so my first steps are to:

1. Replace that version with this version (this repo) (Dunno how just yet but sholdn't be too hard)
2. See if the problem is still there
3. If it is, investigate any '-moncommands' lines and see if I can't get this working.

The context of all of this is I just want to get this debugger working as advertised; will be super helpful to see the contents of memory without having to scroll around the emulator.. also to step through etc. in the normal debugger way.

-----

# VS Code Kick Assembler Studio

Code your way into the past with full support for kick assembler in visual studio code!
Support for debugging using vice, hover text showing contextual help, on the fly error evaluation and automatic tasks generation.

![commodore 64 logo](https://upload.wikimedia.org/wikipedia/commons/2/2c/Commodore_64_logo.png)

## Features

### Contextual help
![test](https://user-images.githubusercontent.com/35506206/76687921-3442c880-6620-11ea-970e-11da9f0aa085.gif)

### On the fly error evaluation
![onflyerrors](https://user-images.githubusercontent.com/35506206/76908128-e805bb80-689f-11ea-88bb-140e626399ad.gif)

### Search for references and go to definition
![Follow reference](https://user-images.githubusercontent.com/35506206/89225416-10cde980-d5d2-11ea-9747-4fc406f57fd1.png)

### Automatic tasks generation
![taskgeneration](https://user-images.githubusercontent.com/35506206/77233973-07079480-6ba3-11ea-8c75-89c292cfeb8f.gif)

### Vice Debugger
![vice debugger](https://user-images.githubusercontent.com/35506206/77234972-22c26900-6baa-11ea-9bec-050480c9376d.gif)

### Watch formated labels and memory addresses
![watches](https://user-images.githubusercontent.com/35506206/89222951-d3fff380-d5cd-11ea-86c0-ce3bca251c5f.png)
You can watch the value of a particular memory address or label. The format can be determinate in this way

(\*|\#)(type:)labelOrAddress([length])

*Examples:*
- message  <-  Will show the value of the label 'message' in hexadecimal , as hexadecimal is the default value
- c:message <- Will show the value of the label 'message' in character, just one character
- c:message[11] <- Will show 11 consecutive values in charactes or a string of length 11 if you will  starting from the lable 'message'
- #message <- Will show the memory address of the label 'message'
- \*c:pointerToMessage[11] <- Will use the memory address (2 bytes) in the label pointerToMessage (in litte endian, lower byte first, hight byte second, watch that value and format it as a string of length 11
- \*\*c:pointerToPointer[11] <- will apply the same indirection twice, so if pointerToPointer contains the memory address of pointerToMessage, and pointerToMessage contains the memory addres of message, this will show the content of message formated in a string of length 11

*Types*
- h: hexadecimal, the default type. Is not necessary to specify it
- d: decimal
- b: binary
- c: character
- l: boolean, will show False if the value of the content is 0, True otherwise




## Configuration options
- `kickass-studio.kickAssJar`: "Full path to KickAss.jar"
- `kickass-studio.javaBin`: "Full path to java binary"
- `kickass-studio.viceBin`: "Full path to VICE binary"
- `kickass-studio.outputDir`: "The default output directory for the compiled program"

## Credits

Santiago Montero

https://github.com/sanmont

https://twitter.com/sanmonterodev

Special thanks to Captain JiNX for his great vscode-kickass extension which code was partially used to develop this extension.
(Used under MIT license)

Check out his awesome extension!

https://github.com/CaptainJiNX/vscode-kickass-c64
