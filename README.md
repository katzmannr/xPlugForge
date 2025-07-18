# xPlugForge
A tool to plug-in modular parts from Bethesda games and forge them

# Motivation
Working with the xEdit tool since years on Bethesda games showed me that it needs modernization.
Since arrival of SteamDeck these games are modded on multiple platforms but this family does only support one platform.
The code base is ancient and so are the tools. For others it is difficult to make their own contributions.

# Steps (open for suggestions)
1. Developing a solid software architecture that makes it both easy to port code as well as add new extensions
2. Use modern UI toolkit that runs on multiple platforms
3. Switch to different, better maintained programming languages
4. Create the new modernized project (file) structure with portability and maintanability in mind
5. Software Design: Decision on design and layout (respecting UI framework, portability, platforms)
6. Program Basics: Creation of Main (command line parsing, necessary classes / instantiation)
7. UI Basics: Creation of Main UI and Handler, Plug-In Selector and Handler)
8. Work on porting "harder parts" like opening, parsing game archives, opening, parsing game modules

# Technical Grinding Details (decided (d), open (o))
a. Tool: Use of multiple programming languages: C++ (backend), Python (application), XML / UI (frontend) (d)

b. Framework: UI/Application: Qt6 Framework. (d)

c. Backend: C++ Framework. Use of Free Pascal for backend could be done for hard to understand parts (o)

d. Bindings: Pascal (no change here). Feature extensions could allow other languages like Python and Lua. (d)

e. API for Bindings: Stay close to original to avoid breaking existing (possibly unmaintained) xedit scripts
   (Legacy API is not planned, xedit API is very flexible) (d)
   
f. Platforms: Linux, Mac, Windows, x64. Portable Platforms only, if Bethesda games run on such platforms (like M1/ARM64) (o)

g. Backend specific: C++ 17/2x, C/C++ classic is unsupported. Compiler: C++ from gnu compiler collection (gcc), llvm / clang C++ Compiler (o)

h. Frontend/UI specific: Python 3.x, Qt 6.8.x (LTS) (d), CMake 4.x (build system) (o)

i. Scripting: Interpreter is part of xedit, port difficulty has not been estimated, but should not have no delphi dependencies (o)

j. Game Archive Parsing: No external (closed source) parts are used, is known to work with archives from latest game engine. (d)

k. Plugable Game Modules: No external (closed source) parts are used, is known to work with modules from latest game engine. (d)

l. Game support: All games, that are supported by the original (potentially focussing the more popular games) (o)

# License
Mozilla Public license 2.0

# References
xEdit: https://github.com/TES5Edit/TES5Edit, https://tes5edit.github.io/
QT6: https://wiki.qt.io/Qt_6.8_Release
GCC: https://gcc.gnu.org/
Clang: https://clang.llvm.org/
Bethesda Games: https://www.reddit.com/r/skyrimmods/wiki/guides_and_resources/, https://www.afkmods.com/index.php?/forum/355-bethesda-games/

# Remarks
This project in no way sees itself as an alternative or replacement of xEdit. the goals are to get the original to a modern platform and modernize the toolkit into something beyond the goals of the xEdit but limiting itself as the original: It is not meant as a game creator for Bethesda games but as a tool for managing and improving the plug-ins created with the creation toolkit from Bethesda.
