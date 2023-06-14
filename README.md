# demo openapi

## コードの自動生成

https://github.com/OpenAPITools/openapi-generator

```shell
# サーバーサイドのコード生成
# python-fastapi
rm -rf ./out && openapi-generator-cli generate -g python-fastapi -i ./openapi.yaml -o ./out

# kotlin client
rm -rf ./out && openapi-generator-cli generate -g kotlin -i ./openapi.yaml -o ./out

# Kotlin spring
# https://openapi-generator.tech/docs/generators/kotlin-spring
rm -rf ./out && openapi-generator-cli generate \
  -g kotlin-spring \
  -i ./openapi.yaml \
  -o ./out \
  --additional-properties=library=spring-boot,serviceImplementation=true

# モックサーバー起動
prism mock openapi.yaml

curl http://localhost:4010/articles
```
