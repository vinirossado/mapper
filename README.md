# Mapper Package

The `mapper` package provides a utility for mapping fields from a source slice to a destination slice of the same struct type. It takes advantage of the generic feature introduced in Go 1.18 to ensure type safety and reusability.

## Usage

```go
package main

// Map maps fields from source slice to destination slice or source to destination struct.
// Both source and destination must be slices of the same struct type.

import (
    "fmt"
    "github.com/vinirossado/mapper"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    sourcePeople := []Person{
        {Name: "John", Age: 30},
        {Name: "Alice", Age: 25},
    }

    var destinationPeople []Person
    err := mapper.Map(sourcePeople, &destinationPeople)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }

    fmt.Println(destinationPeople)
}
