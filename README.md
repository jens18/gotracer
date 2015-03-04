# gotracer
Go package to communicate with the EPsolar Tracer*BN series solar charge controllers.

It has been tested with an EPsolar Tracer4215BN solar charge controller. Connected to a
computer using the EPsolar provided RJ45 to USB cable. As of today I've only gotten the
cable driver for Windows to work.

## Example
This example read the status from the Tracer and displays in on the screen. The example
is running on Windows. The only change on Mac OS X and Linux is the serial device name,
`COM16` in this example.

```go
package main

import (
	"fmt"
	"log"

	"github.com/spagettikod/gotracer"
)

func main() {
	status, err := gotracer.Status("COM16")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Println(status)
}
```
