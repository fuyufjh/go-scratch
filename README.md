# go-scratch

Minimal container image for Go binaries.

# How to use

**Step 1.** Build with static link

```bash
CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o build/release/my-program main.go
```

**Step 2.** Use following `Dockerfile` to build image

```dockerfile
FROM fuyufjh/go-scratch
ADD ./build/release/my-program /
ENTRYPOINT ["/my-program"]
```

Enjoy it!
