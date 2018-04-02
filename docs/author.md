## 作者検索API
#### 使用例

```go
package main
import (  
  "fmt"  
  "github.com/DMMcomLabo/dmm-go-sdk"  
)  

func main() {
	client := dmm.New("foobarbazbuzz", "dummy-990")
	dmmapi := client.Author
	dmmapi.SetFloorID("40")
	dmmapi.SetInitial("あ")
	dmmapi.SetLength(100)
	dmmapi.SetOffset(1)
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
	rst, err := api.NewProductService("foobarbazbuzz", "dummy-999").SetFloorID("40").SetLength(1).Execute()
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
| フロアID | floor_id | ◯ | FloorID | string |
| 頭文字(50音) | initial | | Initial | string |
| 取得件数 | hits | | Length | int64 |
| 検索開始位置 | offset | | Offset | int64 |