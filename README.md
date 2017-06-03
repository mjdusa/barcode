## Introduction ##
This is a package for GO which can be used to create different types of barcodes.

## Supported Barcode Types ##
* Aztec Code
* Codabar
* Code 128
* Code 39
* EAN 8
* EAN 13
* Datamatrix
* QR Codes
* 2 of 5

## Example ##

This is a simple example on how to create a QR-Code and write it to a png-file
```go
package main

import (
	"image/png"
	"os"

	"github.com/boombuler/barcode"
	"github.com/boombuler/barcode/qr"
)

func main() {
	// Create the barcode
	qrCode, _ := qr.Encode("Hello World", qr.M, qr.Auto)

	// Scale the barcode to 200x200 pixels
	qrCode, _ = barcode.Scale(qrCode, 200, 200)

	// create the output file
	file, _ := os.Create("qrcode.png")
	defer file.Close()

	// encode the barcode as png
	png.Encode(file, qrCode)
}
```

## Documentation ##
See [GoDoc](https://godoc.org/github.com/boombuler/barcode)

To create a barcode use the Encode function from one of the subpackages.
