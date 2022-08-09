# parent-image
A set of parent image for quickly define Dockerfile in the development.
## builder
A build tools with docker and support for multi-language development.

see in docker hub , https://hub.docker.com/r/echolixiaopeng/launcher/tags
### nuitka0.9.1-python3.8
```dockerfile
FROM echolixiaopeng/builder:nuitka0.9.1-python3.8 AS builder

FROM echolixiaopeng/launcher:python3.8-bin AS launcher
COPY --from=builder /app/ .
```

## launcher
A runtime environment loads applications and has them run in container.

see in docker hub , https://hub.docker.com/r/echolixiaopeng/builder/tags
### python3.8-bin
```dockerfile
FROM echolixiaopeng/builder:nuitka0.9.1-python3.8 AS builder

FROM echolixiaopeng/launcher:python3.8-bin AS launcher
COPY --from=builder /app/ .
```
### python3.8-plain
```dockerfile
FROM echolixiaopeng/python3.8-plain
```