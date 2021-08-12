# kratos_env_config
Repository for config issue to read configuration from environment valuable 

## Environment

* go run main.go -conf configs/
* kratos version v2.0.3


## Steps

```
export KRATOS_SCHEME="https"

protoc --proto_path=. --proto_path=./third_party --go_out=paths=source_relative:. proto/config.proto

go run main.go -conf configs/
```

Output

```
ERROR msg=failed to merge config source: yaml: unmarshal errors:
  line 1: cannot unmarshal !!str `https` into map[string]interface {}
panic: yaml: unmarshal errors:
  line 1: cannot unmarshal !!str `https` into map[string]interface {}

goroutine 1 [running]:
main.main()
        /opt/workspace/chase/golang/src/kratos_env_config/main.go:34 +0x393
exit status 2
```