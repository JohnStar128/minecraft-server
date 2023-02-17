---
layout: post
permalink: /minecraft-server/
---

## THIS TUTORIAL IS FOR **JAVA EDITION** ONLY!!!

---

# Downloading the server
      
First you need your server .jar file. This can be aquired from `minecraft.net` or the Minecraft Launcher.

Open the vanilla launcher and select the `Installations` tab

![launcher1](https://i.imgur.com/whQgrM2.png)

Assuming you want to download the latest version, select the profile called `Latest Release`, click the menu button to the right and select `Edit`.
![launcher2](https://i.imgur.com/X2iMbRo.png)

Inside this menu you will see a button to the right of the profile labeled `SERVER`. Clicking that will download the server.jar file for the version you want to play on.
![launcher3](https://i.imgur.com/BIQneRO.png)

Make a new folder on your desktop and save this .jar file to it. I would heavily recommend renaming it to quite literally anything other than `server.jar`, maybe like `minecraft-1.19.3-server.jar` or whatever. Up to you.

---

# Setting up the server

Anyway, now you have your server jar file, you just need to make a script to run it. Go to the folder with the jar and make a new text file and call it `start.bat` (or `start.sh` if you're on Linux).

![folder1](https://i.imgur.com/eTMuT1S.png)

Now we get to the fun part.

Open up the script in a text editor (Notepad, VSCode, Vim, etc) and throw this into it:

`java -jar -Xmx2048M -Xms256M minecraft-1.19.3-server.jar -nogui`

![text1](https://i.imgur.com/JmCsVpi.png)

Now we are going to run this script. If I'm not mistaken, double-clicking it on Windows will run it. If not, you can open a CMD Prompt and navigate to the folder and run it that way.

**NOTE:** This step will fail if you don't have Java configured properly. There's [Quite a few guides out there on how to do this](https://www.freecodecamp.org/news/install-openjdk-free-java-multi-os-guide/), but I don't really know how to help there personally.

The first time you run the script, some stuff will happen. If you get a CMD window and it stays open, you will see this text inside of it.
![text2](https://i.imgur.com/nLx0R5C.png)

But if we go back to our folder, there'll be some new stuff inside it.

![folder2](https://i.imgur.com/MNt5CjZ.png)

There is only one file we _need_ to change here, `eula.txt`.

Inside our `eula.txt`, we just need to change this `eula=false` to `eula=true`.

![text3](https://i.imgur.com/VCtae0T.png)

Another file potentially worth looking into editing is the `server.properties` file. It has many of the settings for the server inside it, from the world name, to the server port you use to connect to, to various gamerules.

The main ones you might want to consider changing are `level-name` and `server-port`.

The `level-name` is just the world name. It defaults to `world` but if you were to use a world with a different name, you would need to come here and change this field to match that world folder name.

The `server-port` is a number that the server uses as it's front door. When you or a friend wants to connect to that server, they need to enter the IP address of the computer or machine hosting the server, and the port defined in this file.

In the case of hosting this server on a remote machine like you see big minigame servers do, you will absolutely want to change this port to something else. But in the case of a small server with some friends hosted off the living room PC, leaving this as the default value is completely fine.

All that is finally out of the way, we can connect to our server!

Run that start script again and we should see some new useful information about the server starting up and generating a world.

![text4](https://i.imgur.com/gywcYbk.png)

---

# Connecting to the server

Finally, we can launch Minecraft and go to the Multiplayer menu. Hit `Add Server` and we can enter the connection info.

The name for the server can be whatever you want. The IP is where it gets a little complicated.

If the machine is hosted off the same computer you are playing on, then you can simply use `localhost:25565` to connect to it.

![game1](https://i.imgur.com/fCX8LOC.png)

If it is hosted off a different computer, but that computer is still on the same internet connection as you, you can use that device's local IP to connect. To do this, open a CMD prompt and type `ipconfig`, and look for the line that says `IPv4`.

![whatismybrowser.com](https://i.imgur.com/vm8gZcG.png)

In this example, it is `192.168.1.60`.

In that case, we can use `192.168.1.60:25565` to connect to our server.

![game2](https://i.imgur.com/BwIvG2x.png)

But now let's say your friend down the street wants to play with you. _this_ is the hard part.

Remember when I said the port is basically the front door to the server? In order for people who are on completely different internet connections to connect to the server, you need to open that front door through your internet router/modem settings.

I personally have no idea how to do this but there are [Many guides out there on how to do it](https://www.noip.com/support/knowledgebase/general-port-forwarding-guide/)

But after all that, you should now be able to play on your new Minecraft server!

![yay](/yay.gif)