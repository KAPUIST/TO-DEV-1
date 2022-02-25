### 파일인지 폴더인지 확인하기

- -rw-r--r-- 첫자리가 - 인것은 non directory 를뜻함
- drwr-xr-x d 는 directory 를 뜻하게 됩니다.

폴더면 d 파일이면 -

쓰기권한 w
읽기권한 r
실행권한 e

#### 폴더나 파일의 권한 정보

4가지 구역으로 나타낼수있습니다

- d/rwx/rwx/rwx
  첫번째는 폴더인지 파일인지 두번째 구역은 user 입니다. 즉 사용자는 읽기 쓰기 실행권한 모두 가지고있습니다 그다음으로 group, other 입니다.

1. user

- user는 파일의 소유자 기본적으로 파일을 만든사람

2. group

- group에는 여러 user 가 포함될수 있다. 그룹에 속한 모든 user 는 파일에대한 동일한 group액세스 권한을 갖습니다. 예를들어 프로젝트 진행시에 유저를 그룹에 추가하여 권한을 관리할수있음

3. other

- 파일에 액세스 권한이 있는 다른 user입니다. 파일을 만들지 않은 다른 모든 user를 의미합니다.

#### chmod 권한 변경 명령어

chmod를 사용하여 권한을 변경하는 방법은 두가지가존재

- 더하기, 빼기 , 할당 액세서 유형을 표기하여 변경하는 symbolic method

```js
chmod g-r filename //그룹에서 읽기 권한을 뺍니다
chmod o+x file name //유저에 실행권한을 추가랍니다

//

chmod a=rw filename //rw권한만을 모두에게 줍니다
chmod u= filename // user모든 권한을 지웁니다
chmod a+rw filename // rw권한을 모두에게 추가합니다

```

- rwx를 3bit로 해석하여, 숫자 3자리로 권한을 표기해서 변경하는 Absolute from

  | permission | number |
  | ---------- | ------ |
  | read       | 4      |
  | write      | 2      |
  | excute     | 1      |

```js
chmod 744 filename //-rwxr--r--
chmod 644 filename //-rw-r--r--
chmod 721 filename //-rwx-w---x
```

### 환경변수

- exprot: 환경변수 확인하기 && 환경변수 임시적용

커멘드를 사용해서 환경변구 값을 확인하고 설정할수있음

```js
export //전체 환경변수 확인
export name="good" // 이런식으로 환경변수값을 저장할수있음
echo $name // 이명령어로 name 이라는 환경 변수에 무슨값이 저장되어있는지 확인할수있음
```
