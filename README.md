golang-jwt-json-api-example
===========================

Simple example of a JSON REST API which uses JSON Web Tokens (JWT) for
authentication.

Install
-------

```sh
go get github.com/afternoon/golang-jwt-json-api-example
```

Run
---

```sh
cd golang-jwt-json-api-example/
go build
./golang-jwt-json-api-example
```

Use
---

```sh
# register a user
$ curl -X PUT -H "Content-Type: application/json" \
       -d '{"email": "user1@example.com", "password": "ex1"}' \
       http://localhost:8080/register
{"sessionToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE0NTc2NTI0NTEsImp0aSI6Ik1LMU82RHJUUnBDYzJ0cmxfQ29XSUE9PSJ9.xx9si3DlDQMpf4qzAXAiXKXr1_8VQ6tqbIwOw8rrZfg"}

# get user details (a protected resource)
$ curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE0NTc2NTI0NTEsImp0aSI6Ik1LMU82RHJUUnBDYzJ0cmxfQ29XSUE9PSJ9.xx9si3DlDQMpf4qzAXAiXKXr1_8VQ6tqbIwOw8rrZfg" \
       http://localhost:8080/user
{"email":"user1@example.com"}
```
