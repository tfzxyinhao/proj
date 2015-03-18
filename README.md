[![GoDoc](https://godoc.org/github.com/tfzxyinhao/proj?status.svg)](https://godoc.org/github.com/tfzxyinhao/proj)

# goStart
This is some basic source code of web api,
you can use this source code for making or customizing your own web api


------
#Why
As you all know express framework is very popular in nodejs,and it's also very convenience for web developers and
many developers are using them to build applications.
now i am moving to golang and i can't find noting similar to nodejs express framework in golang
althought it has gin,recel framework etc, but i still can't adjust to it.
so i wrote these basic code to providing router that functionality similar to express 3.x


#Feature：

> * base route like express 3.x
> * url param
> * base json serialize
> * some convenient function

#TODO：

> * form parse wrap
> * base json deserialization

#Usage

```go
	handler := NewHanlder()
	handler.AddRouter("/user/login", func(c *context.Context) {
		j := NewJson()
	    j.BeginObject("user")
		j.BeginArray("products")
		j.BeginObject("")
		j.Add("id", "123456")
		j.Add("id", 3.1415926)
		j.EndObject()
		j.EndArray()
		j.EndObject()
		c.Json(j.ToString())
	})
	handler.Start(":80")
```

#Benchmark

 #Router

PASS
BenchmarkRouter	 1000000	      1018 ns/op
ok  	proj	1.067s

