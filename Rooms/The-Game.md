# The Game - TryHackMe

## What I learned

- .exe is an executable binary file.
- Executable files can contain readable strings.
- The `strings` tool extracts readable text from binary files.
- PowerShell can filter command output using `|`.
- `Select-String` can search for specific text.
- Not every string containing "THM" is a flag.
- More precise filtering can help find the relevant string.
- The challenge description can give clues about the intended technique.

## Tool used

strings

## Command I used

.\strings.exe .\Tetrix.exe | Select-String "THM"

## Main idea

Instead of immediately trying to exploit the program, I first inspected the executable and searched for readable information inside it.