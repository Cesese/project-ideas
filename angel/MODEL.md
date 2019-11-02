# Tree of classes :
```
                +{Visual library -------{qt
                |                       {...
                |
                +{Sound library --------{alsa?
                |                       {...
                |
                +{Video library --------{mpv?
                |                       {vlc?
                |                       {...
                |
Main class -----+
                |
                +{Chat protocols -------{IRC
                |                       {XMPP
                |                       {...
                |
                +{Audio protocols ------{Mumble
                |                       {mp3?
                |                       {ytdl?
                |                       {...
                |
                +{Video protocols ------{Syncplay*
                |                       {ytdl?
                |                       {mkv?
                |                       {ffmpeg?
                |                       {...
                |
                +{Encryption protocols -{OMEMO
                |                       {GPG
                |                       {plain
                |                       {...
                |
```

*Syncplay : I don't think it's a protocol, but it must use some kind of protocol

?mpv/vlc : I know they're used by syncplay. Not sure if we can use them (would be easier), or if there are easy-to-use video libraries, or if it will be a pain

?mp3/mkv : I assume that's the kind of protocols we deal with in audio/video

?alsa : Not sure if we have to go that far, or if there's a universal way to use sound

## Visual library

- Write message in window
- 

## Sound library

idk anything

## Video library

idk anything

## Chat protocol

- Receive messages
- Send message
- Check people in the chat
- Check privacy (omemo, gpg, none, ...)
- 

## Audio protocol

idk anything

## Video protocol

idk anything

## Encryption protocol

- Encrypt
- Decrypt
- Sign?
- Verify?
- 

# Necessary Options

- Changing visuals could be an option (though seems hard to do, if you change from graphical to terminal, but you started it from a file manager, you'll just get it to disappear, and won't find how to close it or get it back to normal)
I think it'd be better to make it so you need to change the code and recompile to use another visual.

- All protocols are available, but not mandatory for a server (we need to have a way to know if two servers from different protocols are part of the same server, for instance with a key signed by the admin, or we trust that when an admin gives a config file to the users, it only has the admin's servers)

- It should be easy to add a server (for instance a list of the supported protocols, and being able to add as many servers as we want for each protocol. There should also be a way to export this kind of configuration and import it back, so that a user doesn't need to know everything, just get the config from the admin and click import)

- Just as it should be easy to add a server, it should be easy to read information about the server (for each protocol the address, port, protocols, admin...). It should also be possible to export that in a readable way.

- There should be an easy way to create a server. Probably a script file that asks questions in a graphical dialog, and installs the required servers and gives the corresponding config file. Should also be easy to uninstall everything.
(not sure about that : in a way the fact that discord allows anyone to create a server means this should exist. But it means having incompetent admins)

# Object example

```java
Class IRC-server {
    
    Attributes :
    
    - private Address // (IPV4, IPV6)
    - private Port
    - private User // (username, password, ... there might be differences between protocols, like on IRC password is not always mandatory, also if we use OMEMO we need the OMEMO keys, etc...)
    
    Methods :
    
    - public Constructors
    
    - public Getters/Setters
    
    - public Encryption = plain
        -Encrypt(message) {
            return message
        }
        -Decrypt(message) {
            return message
        }
    - public Protocol = IRC
        -Send(message) {
        }
        -Receive() {
            return messages
        }
    - public Output = Visual // ? not sure if that should be here or in the main class
        -Process(message) {
            goto correct_line
            goto correct_column
            print message
        }
    
}
```
