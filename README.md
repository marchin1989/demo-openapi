# demo openapi

## コードの自動生成

https://github.com/OpenAPITools/openapi-generator

```shell
# kotlin client
rm -rf ./out && openapi-generator-cli generate -g kotlin -i ./openapi.yaml -o ./out

# kotlin spring server
# https://openapi-generator.tech/docs/generators/kotlin-spring
rm -rf ./out && openapi-generator-cli generate \
  -g kotlin-spring \
  -i ./openapi.yaml \
  -o ./out \
  --additional-properties=library=spring-boot

# モックサーバー起動
prism mock openapi.yaml

curl http://localhost:4010/articles
```
