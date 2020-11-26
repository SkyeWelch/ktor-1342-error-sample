# ktor-1342-error-sample

Sample code to illustrate Ktor 1.4.2 crashing when sending large responses using Jackson.

You can run it with `./gradlew run`.

Succeeding response:
```
→ http localhost:8080/small
HTTP/1.1 200 OK
Connection: keep-alive
Content-Type: application/json; charset=UTF-8
transfer-encoding: chunked

{
    "string": "small string"
}
```

Failing response:
```
→ http localhost:8080/large
HTTP/1.1 200 OK
Connection: keep-alive
Content-Type: application/json; charset=UTF-8
transfer-encoding: chunked


http: error: ChunkedEncodingError: ('Connection broken: IncompleteRead(0 bytes read)', IncompleteRead(0 bytes read))
```
