Get the correct container ID:

```
docker ps
```

Attach to the docker container

```
docker attach [container-id]
```

If your container is configured correctly, you are now attached to the Minecraft server  console

Notify the server that you want to perform save

```
save hold 
```

Check if the server is ready for file copy.

```
save query
```

If yes, then copy the files. Once complete, resume the server.

```
save resume
```

If you don't want to continue, shut the server down gracefully

```
stop
```