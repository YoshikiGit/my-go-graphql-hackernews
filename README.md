## 参考にした Getting Started

[こちら](https://www.howtographql.com/graphql-go/1-getting-started/)

## サーバーの起動

go run ./server.go

## コードの再生成

go run github.com/99designs/gqlgen generate

## createLink の実行

### Premise

- データベースとテーブルが存在
- CreateUser が実行済み

### トークンの生成

```
mutation {
  login(input: {username: "user1", password: "123"})
}
```

### chrome の拡張機能 ModeHeader でトークンを Header に設定

key：Authorization

value：login で得た jwt

### createLink を実行する

```
mutation {
  createLink(input: {title: "real link!", address: "www.graphql.org"}){
    user{
      name
    }
  }
}
```

## Further Steps

If you want to create more complex GraphQL APIs there are few things you can check out:

- Implement voting feature and pagination for the app.
- Read about Relay.
- don’t forget to visit [Learn GraphQL page](https://graphql.org/learn/) to learn more about GraphQL world.
