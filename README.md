# README

Download glide v0.11.0 from the release page https://github.com/Masterminds/glide/releases/tag/v0.11.0 and install in your `PATH` (not your `GOPATH`).

Clone this repo into your `$GOPATH`:

```
$ git clone https://github.com/kwk/broken-glide $$GOPATH/src/github.com/kwk/broken-glide
$ cd GOPATH/src/github.com/kwk/broken-glide
```

Fetch all go dependencies into the `vendor` directory:

```
$ glide install
```

Build goagen

```
$ cd ./vendor/github.com/goadesign/goa/goagen/
$ go build -v
```

Go back to the projects root dir and call goagen

```
$ cd GOPATH/src/github.com/kwk/broken-glide
$ ./vendor/github.com/goadesign/goa/goagen/goagen app -d test/design
```

You should see this error now:

```
invalid plugin package import path: cannot find package "github.com/goadesign/goa/goagen/gen_app" in any of:
  /usr/lib/golang/src/github.com/goadesign/goa/goagen/gen_app (from $GOROOT)
    /home/kkleine/go/src/github.com/goadesign/goa/goagen/gen_app (from $GOPATH)
```


