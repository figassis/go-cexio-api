go-cexio-api
============

Golang API for Cex.io Bitcoin Commodity Exchange.

Example
-------

    package main

import (
    "fmt"

    "github.com/figassis/go-cexio-api"
)

func main() {
    cexapi := cexio.CexKey{Username: "your_username", Api_key: "your_api_key", Api_secret: "your_api_secret"}

    // Public
    if data, err := cexapi.Ticker("GHS/BTC"); err == nil {
        fmt.Printf("Ticker => %s\n", data)
    }

    // Private

    if data, err := cexapi.Balance(); err == nil {
        fmt.Printf("Balance => %s\n", data)
    }

    if data, err := cexapi.OpenOrders("GHS/BTC"); err == nil {
        fmt.Printf("Open Orders => %s\n", data)
    }

    /*
       // Trading orders
       if data, err := cexapi.PlaceOrder("buy", "0.001", "0.017", "GHS/BTC"); err == nil {
           fmt.Printf("Place Order => %s\n", data)
       }

       if data, err := cexapi.CancelOrder("477571539"); err == nil {
           fmt.Printf("Cancel Order => %s\n", data)
       }
    */
}
