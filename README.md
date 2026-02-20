# Pingram Go SDK

Official Go SDK for Pingram - Send notifications via Email, SMS, Push, In-App, and more.

## Installation

```bash
go get github.com/pingram-io/pingram-go
```

## Quick Start

```go
package main

import (
    "context"
    "log"

    pingram "github.com/pingram-io/pingram-go"
)

func main() {
    client := pingram.NewClient("pingram_sk_your_api_key")

    body := pingram.SenderPostBody{
        Type: pingram.PtrString("welcome_email"),
        To: &pingram.SenderPostBodyTo{
            Email: pingram.PtrString("user@example.com"),
        },
        Email: &pingram.SenderPostBodyEmail{
            Subject: "Welcome",
            Html:    "<p>Welcome to our app!</p>",
        },
    }

    _, err := client.Send(context.Background(), body)
    if err != nil {
        log.Fatal(err)
    }
}
```

## Documentation

For full documentation, visit [https://docs.pingram.io](https://docs.pingram.io)
