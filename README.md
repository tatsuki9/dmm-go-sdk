# DMM SDK for Go (v3)
[![GoDoc](https://img.shields.io/badge/go-reference-blue.svg?style=flat-square)](https://godoc.org/github.com/dmmlabo/dmm-go-sdk)
[![License](http://img.shields.io/badge/license-mit-blue.svg?style=flat-square)](https://github.com/dmmlabo/dmm-go-sdk/blob/master/LICENSE)
[![Build Status](http://img.shields.io/travis/dmmlabo/dmm-go-sdk.svg?style=flat-square)](https://travis-ci.org/dmmlabo/dmm-go-sdk)
[![Coverage Status](https://img.shields.io/coveralls/dmmlabo/dmm-go-sdk.svg?style=flat-square)](https://coveralls.io/github/dmmlabo/dmm-go-sdk?branch=master)
[![Go Report Card](https://goreportcard.com/badge/github.com/dmmlabo/dmm-go-sdk)](https://goreportcard.com/report/github.com/dmmlabo/dmm-go-sdk)

DMM Web API version.3 クライアント

参照: [DMM Affiliate](https://affiliate.dmm.com/)

## インストール

`go get` の場合:

```
$ go get github.com/dmmlabo/dmm-go-sdk
```

もしくは

```
$ go get gopkg.in/dmmlabo/dmm-go-sdk.v1
```

## 使い方

使い方や使用例はこちらを参照してください。 [Godoc](https://godoc.org/github.com/dmmlabo/dmm-go-sdk).

## 使用例 (商品検索APIの場合)

```
package main

import (
    "fmt"
    "github.com/dmmlabo/dmm-go-sdk"
    "github.com/dmmlabo/dmm-go-sdk/api"
)

func main() {
	client := dmm.New("dummy-990", "foobarbazbuzz")
	dmmapi := client.Product
	dmmapi.SetSite(api.SiteGeneral)
	dmmapi.SetService("mono")
	dmmapi.SetFloor("dvd")
	dmmapi.SetContentID("15dss00145")
	dmmapi.SetSort("date")
	dmmapi.SetLength(1)
	result, err := dmmapi.Execute()
	if err != nil {
    	fmt.Println(err)
	} else {
    	fmt.Println(result)
	}
}
```

もしくは

```
package main
import (
    "fmt"
    "github.com/dmmlabo/dmm-go-sdk/api"
)
func main() {
	rst, err := api.NewProductService( "dummy-999", "foobarbazbuzz").SetSite(api.SiteAdult).SetLength(1).Execute()
	if err != nil {
    	fmt.Println(err)
	} else {
    	fmt.Println(rst)
	}
}
```

# 詳細

[Godoc](https://godoc.org/github.com/dmmlabo/dmm-go-sdk/api) もしくは [our documentation](https://github.com/dmmlabo/dmm-go-sdk/blob/master/docs/README.md) を参照してください
