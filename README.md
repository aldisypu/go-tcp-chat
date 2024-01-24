# go-tcp-chat
TCP Chat in Go

Once the user connects to the chat server using `telnet` command line program, they can use the following commands to talk to the server:

- `/nick <name>` - get a name, otherwise user will stay anonymous.
- `/join <name>` - join a room, if room doesn't exist, the new room will be created. User can be only in one room at the same time.
- `/rooms` - show list of available rooms to join.
- `/msg	<msg>` - broadcast message to everyone in a room.
- `/quit` - disconnects from the chat server.

## Testing

Now it's time to build, run and test it using `telnet` command.

I'll have 3 terminal windows: one for the server, and another 2 for clients.

```shell
go build .

server started on :8888
```

Client 1:

```shell
telnet localhost 8888
/nick aldi
> all right, I will call you aldi
/join #general
> welcome to #general
> putra joined the room
> putra: Hi
```

Client 2:

```shell
telnet localhost 8888
/nick putra
> all right, I will call you putra
/rooms
> available rooms: #general
/join #general
> welcome to #general
/msg Hi
```