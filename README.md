# snowflake

[![BMC Donate](https://img.shields.io/badge/BMC-Donate-orange)](https://www.buymeacoffee.com/vFa5wfRq6)
[![Build Status](https://travis-ci.org/guoyk93/snowflake.svg?branch=master)](https://travis-ci.org/guoyk93/snowflake)

A concurrent-safe lock-free implementation of snowflake algorithm in Golang

## Get

`go get -u github.com/guoyk93/snowflake`

## Usage

```go
// assign a unique identifier
id, _ := strconv.ParseUint(os.Getenv("WORKER_ID"), 10, 64)

// create a instance
s := snowflake.New(snowflake.Options
  Epoch: time.Date(2020, time.January, 1, 0, 0, 0, 0, time.UTC),
  ID: id,
})

// get a id
s.NewID()

// stop and release all related resource
s.Stop()
```

## Performance

Less than `1us/op`

## Credits
 
Guo Y.K., MIT License
