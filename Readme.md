# BSC GO CLIENT

The BSC go client provides a thin wrapper around bsc endpoints.

## Install

### Requirement

Go version above 1.15

### Use go mod(recommend)

Add "github.com/binance-chain/bsc-go-client" dependency into your go.mod file. Example:
```go
require (
	github.com/binance-chain/bsc-go-client latest
)
```

### Example
```go
import (
	"context"
	
	"github.com/ethereum/go-ethereum/common"
	"github.com/ethereum/go-ethereum/rpc"

	"github.com/binance-chain/bsc-go-client/client"
)


func main() {
	client, _ := client.Dial("wss://bsc-ws-node.nariox.org:443")
	_,e:=client.GetProof(context.Background(),common.HexToAddress("0xa3f020a5c92e15be13caf0ee5c95cf79585eecc9"),[]string{"0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc"}, rpc.BlockNumberOrHashWithNumber(2882160))
	if e!=nil{
		panic(e)
	}
}

```