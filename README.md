# test
name: KIS API Connectivity Check
on: [workflow_dispatch] # 수동으로 버튼 눌러서 실행

jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - name: Test Connection to KIS Server
        run: |
          # 한투 실전투자 서버로 토큰 요청을 날려봅니다 (데이터는 틀려도 상관없음)
          curl -X POST "https://openapi.koreainvestment.com:9443/oauth2/tokenP" \
               -H "Content-Type: application/json" \
               -d '{"grant_type":"client_credentials","appkey":"test","appsecret":"test"}' \
               -v
