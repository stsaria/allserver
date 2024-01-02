# AllServer
## Note
*Be sure to read this before creating and publishing your server.
- This system should be done with some understanding of server/internet knowledge.
  (For example: I have heard of cases where a server was set up, but there was a mistake in opening the ports and your computer became a stepping stone (basically a crime) for something.)
- The `allserver.py` here should be changed to the binary extension if it is a binary. (Linux has no extension).
- There are no rules for this AllServer other than the license.
  The rules are the server's own arrangements.
- This program may be very vulnerable.
- This program may have been written in the description but forgotten to actually implement it. (Sorry.)
- Be sure to be careful with the environment. (Are you using interfering ports? Do you have enough free memory?)

## Overview
AllServer is a minecraft server provisioning system that runs at very low cost and low load.

Even those who cannot open ports can set up a server for free!

Instead of concentrating on one server and running minecraft servers, this system randomly sets up minecraft servers on many supported servers.

There are two types of servers: servers that have a list of servers and servers where you can set up a Minecraft server.

Of course, "you" can also support a server, as long as you have the right memory and ports!

Figure

![](./figure.drawio.png)

## Client & Server
If you cannot open a port but want to create a server, you can use "client" to create a server.

If you can open the port and have enough memory, you can use a "server" to assist you.

Alternatively, you can set up a "list server" that has the servers' information.


[Client](https://github.com/stsaria/allserver-client)
[Server](https://github.com/stsaria/allserver-server)

## ini File
### What is an ini file?
Note: This is not an overview of ini files, but rather a description of the ini files used by AllServer.

An ini file is a configuration file for AllServer.
How to write it is written in each file.
The location is in the 'config' folder.

### List of files
The "basic.ini" file is an ini file that describes the basic AllServer settings (language and team). (It can be found on both client and server)
The "minecraftserver.ini" file is an ini file that describes the AllServer's minecraft server settings (port, version). (Not available on the client)
## Language Files
### What is a language file?
A language file is a written file that appears when using "AllServer".
I, Saria, write in Japanese, but any text that can be expressed in UTF-8 (including environment-dependent text) can be written in a language file.
Creation and Writing Methods
The language file should be created in the "lang" folder as "language name.json" and written. (The contents differ between the client and server.)
For Japanese language files, see "ja.json".(Server or Client)

Sentences with many newlines are written using an array.

ja.json
```json
"ModeSelectMessage":
["モードを選択してください。\n",
"[1] : クライアントモード（サーバー作成・検索）",
"[2] : マインクラフトサーバーモード（サーバー支援・リストに登録）",
"[3] : リストサーバーモード（マインクラフトサーバーリスト）",
"[4] : 終了"
]
```
Of course, non-array writing methods (e.g., multi-line strings) are also possible, but they all violate the rules of the **Json standard** and are therefore not used.

### How to load

To load a language file, enter the name of the language file without its extension in the "lang/lang" key of "basic.ini" in the "config" file

basic.ini
```ini
[lang]
lang = ja
spare_lang = us
```
