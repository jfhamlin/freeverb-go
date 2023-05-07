# freeverb-go

A Go implementation of the Freeverb reverberator.

See readme.txt for the original Freeverb README.

## Installation

```bash
go get github.com/jfhamlin/freeverb-go
```

## Usage

```go
import "github.com/jfhamlin/freeverb-go"

var (
	revmod = freeverb.NewRevModel()
)

func Process(wet, damp, roomSize float32, inputLeft, inputRight []float32) (left, right []float32) {
	// See godoc for a full list of parameters
	revmod.SetWet(wet)
	revmod.SetDamp(damp)
	revmod.SetRoomSize(roomSize)

	n := len(input)
	outputLeft := make([]float32, n)
	outputRight := make([]float32, n)
	revmod.ProcessReplace(inputLeft, inputRight, outputLeft, outputRight, n, 1)
	return outputLeft, outputRight
}
```

## License

MIT
