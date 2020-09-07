# GoInk
simple go web framework.
### Sample
```
package main

import "github.com/Snowitty/Ink"

var (
	app *Ink.App
)

func init() {
	// init new application.
	// it loads default config file "config.json". if not exist, use pre-defined config.
	app = Ink.New()
}

// default handler, implement Ink.Handler
func homeHandler(ctx *Ink.Context) {
	ctx.Body = []byte("Hello Ink !")
}

func main() {
	// only bind GET handler by homeHandler.
	// if other http method, return 404.
	app.Get("/", homeHandler)

	// run application.
	// it listens localhost:9000 in pre-defined config.
	app.Run()
}

```
### License

Apache License 2.0