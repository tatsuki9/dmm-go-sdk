## フロアAPI
#### 使用例

```go
package main 
import (  
  "fmt"  
  "github.com/DMMcomLabo/dmm-go-sdk"  
)  

func main() {
	client := dmm.New("foobarbazbuzz", "dummy-990")
	dmmapi := client.Floor
	result, err := dmmapi.Execute()
	if err != nil {
	  fmt.Println(err)
	} else {
	  fmt.Println(result)
	}
}
```

もしくは以下のように1行で書くこともできます。

```go
package main
import (
  "fmt"
  "github.com/DMMcomLabo/dmm-go-sdk/api"
)

func main() {
	rst, err := api.NewFloorService("foobarbazbuzz", "dummy-999").Execute()
	if err != nil {
	  fmt.Println(err)
	} else {
	  fmt.Println(rst)
	}
}
```

#### リクエストパラメータ
APIのパラメータとSDKのパラメータの関連について

| 論理名 | API (物理名) | 必須 | SDK | データ型 |
|---|---|:---:|---|---|
| API ID | api_id | ◯ | ApiID | string |
| アフィリエイトID | affiliate_id | ◯ | AffiliateId | string |

