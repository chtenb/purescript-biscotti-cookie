# purescript-cookie-parser

This library allows parsing and generating cookie headers. You'll generally use
the `Cookie.new` function to create a cookie from a key/value pair and the
`Cookie.set*` functions to set attributes on a cookie.

`Cookie.toString` generates the string representation of a cookie, suitable for
writing to an HTTP header.

`Cookie.parse` parses the string representation of a cookie, returning an
`Either ParseError Cookie`.

```purescript
import HTTP.Cookie as Cookie

> Cookie.toString $ Cookie.setSecure $ Cookie.new "key" "value"
key=value; Secure

> Cookie.parse "key=value; Secure"
(Right { domain: Nothing, expires: Nothing, httpOnly: false, maxAge: Nothing, name: "key", path: Nothing, secure: true, value: "value" })
```

## Running the tests

```text
spago test
```

## License

MIT
