### Origin transaction data to Digest


We use [`SHA-2`](https://en.wikipedia.org/wiki/SHA-2) algorithm to generate  `Digital Digest`.


Here is example by Golang:


```go
package main

import (
	"crypto/sha256"
	"encoding/json"
	"fmt"
)


type Trade struct {
	UserID     string `json:"user_id"`
	Ticket     string `json:"ticket"`
	Symbol     string `json:"symbol"`
	Cmd        string `json:"cmd"`
	Volume     string `json:"volume"`
	OpenTime   int64  `json:"open_time"`
	OpenPrice  string `json:"open_price"`
	CloseTime  int64  `json:"close_time"`
	ClosePrice string `json:"close_price"`
}



//jsonData
func main() {

	t := &Trade{
		UserID:     "100001",     //
		Ticket:     "20000001",   // transaction_id in tradeing system
		Symbol:     "XAUUSD200",  // 
		Cmd:        "0",          //  type buy or sell type
		Volume:     "10",      
		OpenTime:   1534301400, 
		OpenPrice:  "1190.25",
		CloseTime:  0,
		ClosePrice: ""}

	jsonData, _ := json.Marshal(t)


	sha_256 := sha256.New()
	sha_256.Write(jsonData)
	digest := fmt.Sprintf("%x", sha_256.Sum(nil))

	fmt.Println(digest)
	// a40dc43d3663d3371b0b306d93567fb4061bec20819a3ad1942ec35385969042

}

```
