// Package mapper provides a utility for mapping fields from a source struct/slice to a destination struct/slice of the same type.
//
// Usage:
//
// 		// Map fields from source struct to destination struct
// 		err := mapper.Map(&sourceStruct, &destinationStruct)
//
// 		// Map fields from source slice to destination slice
// 		err := mapper.Map(&sourceSlice, &destinationSlice)
//
// 		// Supported types for mapping are: struct and slice of structs.
// 		// Note that the order of fields in the struct is not significant.
//
// Errors:
//
// If the provided source and destination types are not of the same kind (struct or slice), an error will be returned.
// If there is a type mismatch between fields, an error will be returned.
//
// Example:
//
// 		package main
//
// 		import (
// 			"fmt"
// 			"github.com/yourusername/mapper"
// 		)
//
// 		type Person struct {
// 			Name string
// 			Age  int
// 		}
//
// 		func main() {
// 			source := Person{Name: "John", Age: 30}
// 			var destination Person
//
// 			err := mapper.Map(&source, &destination)
// 			if err != nil {
// 				fmt.Println("Error:", err)
// 				return
// 			}
//
// 			fmt.Println(destination.Name) // Output: "John"
// 			fmt.Println(destination.Age)  // Output: 30
// 		}
//
package github.com/vinirossado/mapper