# Custom Error in ES6

```js
class CustomError extends Error {
    constructor(message) {
        super(message)
    }
}

throw new CustomError('Opps')
// Error: Opps
//    at CustomError <FileDir>:<LineNumber>:<ColNumber>
//    at Object... <FileDir>:<LineNumber>:<ColNumber>


// Better stack trace
class CustomError extends Error {
    constructor(message) {
        super(message)
        Error.captureStackTrace(this, this.constructor)
        this.name = this.constructor.name
    }
}
throw new CustomError('Opps')
// CustomError: Opps
//    at Object... <FileDir>:<LineNumber>:<ColNumber>

```



Reference

* [https://www.loggly.com/blog/node-js-error-handling/](https://www.loggly.com/blog/node-js-error-handling/)



