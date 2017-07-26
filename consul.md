# Consul

Get specific key

```
$ consul kv get <PATH>/<KEY>
```

List all keys

```
$ consul kv get -recurse
```

Update existing key

```
$ consul kv put <PATH>/<KEY>
```

## Consul Template

split value and loop

```
# somepath/hello=foo,bar
{{ $hello := key(print "somepath/hello") | split "," }}

{{ range $hello }}
Show me {{.}}{{end}}
# Output
# Show me foo
# Show me bar
```



