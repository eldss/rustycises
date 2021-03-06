In the Gophercises course, this exercise works with the Go standard library to create an HTTP handler function that returns a closure to handle url redirects. Rust does not have a the same kind of http standard library functionality as Go does, so I have to use an external crate to adhere to. I've opted for Rocket because it is the web framework that I want to learn most.

While Rocket does have the Handler trait, I've found it difficult to figure out how to use it in the same way as the http.HandlerFunc is used in Go. Rocket has a more specific purpose than the net/http library in Go. Instead of trying to replicate the exercise exactly, I will instead build a rocket server that works as a url shortener, with specific endpoints to add url mappings and another to redirect a request based on those mappings.

---

Working with Rocket has been more difficult than I expected for this task. I tried using a simple HashMap for storage, but kept getting compile errors about lifetimes on a function that used Rocket's State, but the docs do not look like what the compiler wanted. I also tried using Diesel to integrate a database, but that got very confusing as well.

Thankfully I have found a book that helps with structuring web apps using Diesel and Rocket (and Seed for UI via WebAssembly, but that is not used here). The book can be found [here](https://erwabook.com/). This exercise follows the structure presented there.