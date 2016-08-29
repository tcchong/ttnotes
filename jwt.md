# JSON Web Token(JWT)

> JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.
>
> https://jwt.io/


### Format

> [Header].[Payload].[Signature]

```
# Sample JWT
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiMTIzIiwiaWF0IjoxNDcyNDM2NDc1LCJleHAiOjE0NzI0NDAwNzV9.A2QHa4uQXLMUk7lgb_-NshsWUpaRZQeRQ0flvkkrjNI

# Header
{"alg":"HS256","typ":"JWT"}

# Payload
{"user":"123","iat":1472436475,"exp":1472440075}

# Verify Signature
HMACSHA256( base64UrlEncode(header) + "." + base64UrlEncode(payload), <SECRET_KEY>)

```

