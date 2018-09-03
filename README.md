# Requestly - Simple REST Request library for Go (golang)

[![Go Report](https://goreportcard.com/badge/github.com/apibillme/requestly)](https://goreportcard.com/report/github.com/apibillme/requestly) [![Travis](https://travis-ci.org/apibillme/requestly.svg?branch=master)](https://travis-ci.org/apibillme/requestly#) [![codecov](https://codecov.io/gh/apibillme/requestly/branch/master/graph/badge.svg)](https://codecov.io/gh/apibillme/requestly) ![License](https://img.shields.io/github/license/mashape/apistatus.svg) ![Maintenance](https://img.shields.io/maintenance/yes/2018.svg) [![GoDoc](https://godoc.org/github.com/apibillme/requestly?status.svg)](https://godoc.org/github.com/apibillme/requestly)


This small REST request library combines [fasthttp](https://github.com/valyala/fasthttp#readme) for performance, [gjson](https://github.com/tidwall/gjson#readme) for JSON searching, and [etree](https://github.com/beevik/etree#readme) for XML searching.

```bash
go get github.com/apibillme/requestly
```

```go
req := requestly.New()

req.Header.Add("Authorization", "Bearer my_token")

jsonBody := `{"key":"value"}`

xmlBody := `<?xml version="1.0" encoding="UTF-8"?><People><Person name="Jon"/></People></xml>`

res, err := requestly.GetJSON(req, "https://mockbin.com/request")
	
res, err := requestly.DeleteJSON(req, "https://mockbin.com/request")
	
res, err := requestly.PutJSON(req, "https://mockbin.com/request", jsonBody)
	
res, err := requestly.PostJSON(req, "https://mockbin.com/request", jsonBody)
	
res, err := requestly.PatchJSON(req, "https://mockbin.com/request", jsonBody)

res, err := requestly.GetXML(req, "https://mockbin.com/request")
	
res, err := requestly.DeleteXML(req, "https://mockbin.com/request")
	
res, err := requestly.PutXML(req, "https://mockbin.com/request", xmlBody)
	
res, err := requestly.PostXML(req, "https://mockbin.com/request", xmlBody)
	
res, err := requestly.PatchXML(req, "https://mockbin.com/request", xmlBody)
```
