# Lerna Guide
Lerna는 git 및 npm을 사용하여 다중 패키지 리포지토리를 관리하는 작업 흐름을 최적화하는 도구입니다.
https://lerna.js.org/

## 시작하기
npm 을 사용하여 Lerna를 전역 적으로 설치하는 것으로 시작하겠습니다 .
Lerna 2.x는 시작하기에 권장되는 버전입니다.

```sh
npm install --global lerna
```
다음으로 새 git 저장소를 생성합니다.

```sh
git init lerna-repo && cd lerna-repo
```

이제 Lerna 리포지토리로 바꾸겠습니다.

```sh
lerna init
```

이제 저장소는 다음과 같아야합니다.
```sh
lerna-repo/
  packages/
  package.json
  lerna.json
```

## 명령어
