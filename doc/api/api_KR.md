# Grin API 문서

이 문서는 3가지 Grin REST API에 대해서 설명합니다.
이 엔드포인트들은 2가지 카테고리로 묶입니다.

## Node API

이 엔드포인트는 블록체인과 네트워크, 피어들의 다양한 정보에 대해서 노드에게 질의(Query, 쿼리)하는데 사용합니다.
기본적으로 이 REST API는 `localhost:3413` 에서 작동하고 Grin 노드와 함께 시작합니다.

이 엔드포인트는 기본적으로 [Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)이 필요합니다.
유저 이름은 `grin` 이고 패스워드는  `.api_secret` 파일에서 찾으실 수 있습니다.
좀 더 자세한 API call에 대해서 알고 싶으시다며 [한글 node API 문서](node_api_KR.md)를 참고하세요.

## Wallet APIs

### Foreign Wallet API

The foreign API is an endpoint mainly designed to receiving grins through a network. This REST API can be started with the `grin wallet listen` command and by default will listen on `localhost:3415`.
To learn about what specific calls can be made read the [wallet foreign API doc](wallet_foreign_api.md).

### Wallet Owner API

The wallet owner API is an endpoint to manage the user wallet: broadcast transaction, sign transaction, see the current balance... This REST API can be started with the `grin wallet owner_api` command and will listen on `localhost:3420`.

__This endpoint must **never** be exposed to the outside world.__

This endpoint requires, by default, Basic Authentication. The username is `grin` and the password can be found in the `.api_secret` file.
To learn about what specific calls can be made read the [wallet owner API doc](wallet_owner_api.md).

## Ports above 10000?

All ports should be below 10000 when running with default settings on mainnet. If your grin owner_api is using the 13420 port but is on mainnet, then you're using an outdated version of grin.
