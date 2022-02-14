## OAUTH 2.0

### OAUTH 란?

OAuth2.0은 인증을 위한 표준 프로토콜의 한 종류
보안 된 리소스에 액세스하기 위해 클라이언트에게 권한을 제공(Authorization)하는 프로세스를 단순화하는 프로토콜 중 한 방법이다.

### OAUTH 사용시 알아야할 필수용어!!!!

- Resource Owner : 액세스 중인 리소스의 유저입니다. 김코딩의 구글 계정을 이용하여 App에 로그인할 경우, 이때 Resource owner은 김코딩이 됩니다.
- Client : Resource owner를 대신하여 보호된 리소스에 액세스하는 응용프로그램입니다. 클라이언트는 서버, 데스크탑, 모바일 또는 기타 장치에서 호스팅 할 수 있습니다.
- Resource server : client의 요청을 수락하고 응답할 수 있는 서버입니다.
- Authorization server : Resource server가 액세스 토큰을 발급받는 서버입니다. 즉 클라이언트 및 리소스 소유자를 성공적으로 인증한 후 액세스 토큰을 발급하는 서버를 말합니다.
- Authorization grant : 클라이언트가 액세스 토큰을 얻을 때 사용하는 자격 증명의 유형입니다.
- Authorization code : access token을 발급받기 전에 필요한 code입니다. client ID로 이 code를 받아온 후, client secret과 code를 이용해 Access token 을 받아옵니다.
- Access token : 보호된 리소스에 액세스하는 데 사용되는 credentials입니다. Authorization code와 client secret을 이용해 받아온 이 Access token으로 이제 resource server에 접근을 할 수 있습니다.
- Scope : scope는 토큰의 권한을 정의합니다. 주어진 액세스 토큰을 사용하여 액세스할 수 있는 리소스의 범위입니다.

### im-sprint-auth-oauth

server

1. Github OAuth를 이용한 로그인 구현!!

https://www.oauth.com/oauth2-servers/accessing-data/create-an-application/ 참고!!

2.callback.js

```js
axios({
    method: "POST",
    url: "https://github.com/login/oauth/access_token",
    header: {
      accept: "application/json",
    },
    data: {
      client_id: clientID,
      client_secret: clientSecret,
      code: req.body.authorizationCode,
    },
  })
    .then((data) => {
      const accessToken = data.data.access_token;
      console.log(accessToken);
      res.status(200).send({ accessToken: accessToken });
    })
    .catch((err) => {
      res.status(400);
    });
};
```

console.log 를 많이 찍어봐야 눈에 구도가 그려진다

axios 사용법에대해서 헷갈렷는데 다시한번 공부하는 계기가 됨

3.images.js
별거없엇다 테스트 케이스만 봐도 답이 무엇인지 알수있었으나 {message: ...}이부분 빼먹어서 오래걸렷다

### client

개인적으로 잘풀리지 않아서 엄청나게 시간을 많이 쓴곳

#### login

이부분은 참고: https://docs.github.com/en/free-pro-team@latest/developers/apps/identifying-and-authorizing-users-for-github-apps

이것만 잘따라하면 문제없이 통과할수있다.

#### Mypage.js

유저인포 부분이나 이미지를 불러오는 부분 쉽게 해결하엿으나 리액트에서 막힌것인지 인증에서 막힌것인지 감도못잡고 해멧다.
이부분 2시간가까기 고민햇다 풀기가 너무 힘들엇다 저녁이 되어서 피곤해서 그런지 집중조차안됫다 결국 레포코드를 모고 풀게되엇다.

### app.js

이부분 역시 쉽지않았다 axios 에 익숙하지 않아 발생한 문제로 생각된다.

찾아보니 따로 변수로 지정해서 사용하시는방법이 많더라 그냥 axios.post()로하다가 잘안되었다 정확히 무엇을못한것인지 파악이 필요하다.

```js
const data = await axios
      .post("http://localhost:8080/callback", {
        authorizationCode: authorizationCode,
      })
      .then((res) => {
        console.log(res.data);
        return res.data;
      });
    console.log();
    this.setState({
      isLogin: true,
      accessToken: data.accessToken,
    });
  }
```
