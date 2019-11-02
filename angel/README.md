Name : Angel 

+-----------+-----------------------------+
| Language  | Java? C++? -> OOP           |
+-----------+-----------------------------+
| Urgent    | No (discord is good enough) |
+-----------+-----------------------------+

# Ideas

- Needs to be usable anywhere
(first I thought about doing a webapp like Discord,
but sounds pretty hard to do, and there are restrictions.
So right now I'm thinking of using Java)
(Now apparently we should use c++ because it allows the use of qt. Need
to check if building in c++ is as easy to port on all platforms as say java)
- For voice : mumble
- For text : xmpp + omemo ; IRC ; allowing compatibility with others chat clients
- For video : idk
- Using syncplay to watch stuff together
- Maybe usable with discord servers? (though with a warning)
- Maybe usable with slack? (same)
- Easily customizable : adding themes, other protocols, etc... should be easy to do
- GPL3 license
- Good UI/UX (never know which is which) ; Easy to use for everyone
- If it's built in Java : must be compilable for Windows, Mac, Linux, Android
(need to avoid using platform-specific libraries!)
(maybe iOS too? idk if it's possible, and how much it costs)
- There must be a client, and a server for each protocol
(we could try to make it easy to create a server)
- Must be modular : 
    - easy to implement new visuals
    (if I want to change from qt to ncurses for instance)
    - easy to implement new protocols
    (if I want to use teamspeak instead of mumble for instance)


```
+--------+                       +---------------+
| Client |<------------+-------->| Mumble server |
+--------+             |         +---------------+
                       |         +------------+
                       +-------->| IRC server |
                       |         +------------+
                       |         +-------------+
                       +-------->| XMPP server |
                       |         +-------------+
                       |
```
