## 女優検索API
#### 使用例

```go
package main
import (  
  "fmt"  
  "github.com/DMMcomLabo/dmm-go-sdk"  
)  

func main() {

	client := dmm.New("foobarbazbuzz", "dummy-990")
	dmmapi := client.Actress
	dmmapi.SetInitial("あ")
	dmmapi.SetKeyword("あさみ")
	dmmapi.SetBust("90")
	dmmapi.SetWaist("-60")
	dmmapi.SetHip("85-90")
	dmmapi.SetHeight("160")
	dmmapi.SetBirthday("19900101")
	dmmapi.SetSort("-name")
	dmmapi.SetLength(20)
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
	rst, err := api.NewActressService("foobarbazbuzz", "dummy-999").SetLength(1).Execute()
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
| 頭文字(50音) | inital | | Initial | string |
| キーワード | keyword | | Keyword | string |
| バスト | bust | | Bust | string |
| ウエスト | waist | | Waist | string |
| ヒップ | hip | | Hip | string |
| 身長 | height | | Height | string |
| 生年月日 | birthday | | Birthday | string |
| 取得件数 | hits | | Length | int64 |
| 検索開始位置 | offset | | Offset | int64 |
| ソート順 | sort | | Sort | string |