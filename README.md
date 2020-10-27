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
다음은 각 명령에 대한 간략한 소개입니다. 자세한 정보 는 [README](https://github.com/lerna/lerna#readme) 를 참조하십시오.

- `lerna init`
새 lerna 리포지토리를 생성하거나 기존 리포지토리를 현재 버전의 Lerna로 업그레이드합니다.
**옵션**
`--independent` or  `-i` 독립 버전 관리 모드를 사용합니다.
<br>
- `lerna bootstrap`
현재 Lerna 저장소에서 패키지를 부트 스트랩합니다. 모든 종속성을 설치하고 상호 종속성을 연결합니다.
이 명령을 사용 require()하면 패키지가 이미 존재하고 node_modules폴더 에서 사용 가능한 것처럼 패키지 이름을 사용할 수 있으므로 매우 중요 합니다.
<br>
- `lerna import <pathToRepo>`
로컬 경로 <pathToRepo>의 패키지를 커밋 기록이있는 packages / <directory-name>으로 가져옵니다.
<br>
- `lerna publish`
업데이트 된 패키지의 새 릴리스를 만듭니다. 새 버전을 요청하고 git 및 npm의 모든 패키지를 업데이트합니다.
**옵션**
`--npm-tag [tagname]` — 주어진 npm dist-tag를 사용하여 npm에 게시합니다 (기본값은 최신).
`--canary/ -c` – 카나리아 릴리스를 만듭니다.
`--skip-git` – git 명령을 실행하지 마십시오.
`--force-publish [packages]` — 지정된 패키지 (쉼표로 구분) 또는 모든 패키지에 대해 강제 게시합니다 ( *변경된 패키지에 대한 git diff 검사 건너 뛰기).

- `lerna changed`
마지막 릴리스 이후 변경된 패키지를 확인하십시오.

- `lerna diff [package?]`
마지막 릴리스 이후 모든 패키지 또는 단일 패키지를 비교하십시오.

- `lerna run [script]`
해당 스크립트가 포함 된 각 패키지에서 npm 스크립트 를 실행하십시오 .

- `lerna ls`
현재 Lerna 저장소의 모든 공개 패키지를 나열합니다.

## Lerna를 사용하는 프로젝트
<ul>
  <li><a href="https://github.com/primer/primer">primer/primer</a></li>
  <li><a href="https://github.com/babel/babel">babel/babel</a></li>
  <li><a href="https://github.com/facebook/create-react-app">facebook/create-react-app</a></li>
  <li><a href="https://github.com/ReactTraining/react-router">ReactTraining/react-router</a></li>
  <li><a href="https://github.com/pugjs/pug">pugjs/pug</a></li>
  <li><a href="https://github.com/facebook/jest">facebook/jest</a></li>
  <li><a href="https://github.com/reactotron/reactotron">reactotron/reactotron</a></li>
  <li><a href="https://github.com/ElemeFE/mint-ui">ElemeFE/mint-ui</a></li>
  <li><a href="https://github.com/devtools-html/debugger.html">devtools-html/debugger.html</a></li>
  <li><a href="https://github.com/alibaba/rax">alibaba/rax</a></li>
  <li><a href="https://github.com/Turfjs/turf">Turfjs/turf</a></li>
  <li><a href="https://github.com/babel/babili">babel/babili</a></li>
  <li><a href="https://github.com/storybooks/storybook">storybooks/storybook</a></li>
  <li><a href="https://github.com/xmppjs/xmpp.js">xmppjs/xmpp.js</a></li>
  <li><a href="https://github.com/wooorm/retext">wooorm/retext</a></li>
  <li><a href="https://github.com/jumpsuit/jumpsuit">jumpsuit/jumpsuit</a></li>
  <li><a href="https://github.com/strapi/strapi">strapi/strapi</a></li>
  <li><a href="https://github.com/cloudflare/cf-ui">cloudflare/cf-ui</a></li>
  <li><a href="https://github.com/colmena/colmena">colmena/colmena</a></li>
  <li><a href="https://github.com/angus-c/just">angus-c/just</a></li>
  <li><a href="https://github.com/cerebral/cerebral">cerebral/cerebral</a></li>
  <li><a href="https://github.com/nteract/nteract">nteract/nteract</a></li>
  <li><a href="https://github.com/wooorm/remark">wooorm/remark</a></li>
  <li><a href="https://github.com/rofrischmann/fela">rofrischmann/fela</a></li>
  <li><a href="https://github.com/tbranyen/diffhtml">tbranyen/diffhtml</a></li>
  <li><a href="https://github.com/ElemeFE/cooking">ElemeFE/cooking</a></li>
  <li><a href="https://github.com/antwarjs/antwar">antwarjs/antwar</a></li>
  <li><a href="https://github.com/apollostack/graphql-server">apollostack/graphql-server</a></li>
  <li><a href="https://github.com/jimpick/lambda-comments">jimpick/lambda-comments</a></li>
  <li><a href="https://github.com/lystable/recon">lystable/recon</a></li>
  <li><a href="https://github.com/marudor/flowInterfaces">marudor/flowInterfaces</a></li>
  <li><a href="https://github.com/GoogleChrome/sw-helpers">GoogleChrome/sw-helpers</a></li>
  <li><a href="https://github.com/webpack-preset/webpack-preset">webpack-preset/webpack-preset</a></li>
  <li><a href="https://github.com/vazco/uniforms">vazco/uniforms</a></li>
  <li><a href="https://github.com/metal/metal.js">metal/metal.js</a></li>
  <li><a href="https://github.com/steelbrain/pundle">steelbrain/pundle</a></li>
  <li><a href="https://github.com/neos/neos-ui">neos/neos-ui</a></li>
  <li><a href="https://github.com/mosjs/mos">mosjs/mos</a></li>
  <li><a href="https://github.com/lore/lore">lore/lore</a></li>
  <li><a href="https://github.com/act-framework/act">act-framework/act</a></li>
  <li><a href="https://github.com/yvele/poosh">yvele/poosh</a></li>
  <li><a href="https://github.com/noderaider/gridiron">noderaider/gridiron</a></li>
  <li><a href="https://github.com/superawesomelabs/leo">superawesomelabs/leo</a></li>
  <li><a href="https://github.com/tocco/tocco-client">tocco/tocco-client</a></li>
  <li><a href="https://github.com/zalando-incubator/tessellate">zalando-incubator/tessellate</a></li>
  <li><a href="https://github.com/sencha/extjs-reactor">sencha/extjs-reactor</a></li>
  <li><a href="https://github.com/DigitalRiver/react-atlas">DigitalRiver/react-atlas</a></li>
  <li><a href="https://github.com/forivall/tacoscript">forivall/tacoscript</a></li>
  <li><a href="https://github.com/Boxable/box-ui">Boxable/box-ui</a></li>
  <li><a href="https://github.com/flux-capacitor/flux-capacitor">flux-capacitor/flux-capacitor</a></li>
  <li><a href="https://github.com/trepo/trepo-js">trepo/trepo-js</a></li>
  <li><a href="https://github.com/spacedoc/spacedoc">spacedoc/spacedoc</a></li>
  <li><a href="https://github.com/oknosoft/metadata.js">oknosoft/metadata.js</a></li>
  <li><a href="https://github.com/uber-web/uber-eslint">uber-web/uber-eslint</a></li>
  <li><a href="https://github.com/brittanica/brittanica">brittanica/brittanica</a></li>
  <li><a href="https://github.com/openzipkin/zipkin-js">openzipkin/zipkin-js</a></li>
  <li><a href="https://github.com/vudash/vudash">vudash/vudash</a></li>
  <li><a href="https://github.com/nteract/commuter">nteract/commuter</a></li>
  <li><a href="https://github.com/frintjs/frint">frintjs/frint</a></li>
  <li><a href="https://github.com/fyndiq/fyndiq-ui">fyndiq/fyndiq-ui</a></li>
  <li><a href="https://github.com/azu/immutable-array-prototype">azu/immutable-array-prototype</a></li>
  <li><a href="https://github.com/TrueCar/gluestick">TrueCar/gluestick</a></li>
  <li><a href="https://github.com/KELiON/create-cerebro-plugin">KELiON/create-cerebro-plugin</a></li>
  <li><a href="https://github.com/phenomic/phenomic">phenomic/phenomic</a></li>
  <li><a href="https://github.com/sterjakovigor/vqua">sterjakovigor/vqua</a></li>
  <li><a href="https://github.com/wireapp/wire-web-packages">wireapp/wire-web-packages</a></li>
  <li><a href="https://github.com/klis87/redux-saga-requests">klis87/redux-saga-requests</a></li>
  <li><a href="https://github.com/WordPress/gutenberg">WordPress/gutenberg</a></li>
  <li><a href="https://github.com/react-cosmos/react-cosmos">react-cosmos/react-cosmos</a></li>
  <li><a href="https://github.com/jsbites/jedifocus-monorepo">jsbites/jedifocus-monorepo</a></li>
  <li><a href="https://github.com/FoalTS/foal">FoalTS/foal</a></li>
  <li><a href="https://github.com/emotion-js/emotion">emotion-js/emotion</a></li>
  <li><a href="https://github.com/Bamieh/reflow/">Bamieh/reflow</a></li>
  <li><a href="https://github.com/transloadit/uppy/">transloadit/uppy</a></li>
  <li><a href="https://github.com/olistic/warriorjs">olistic/warriorjs</a></li>
  <li><a href="https://github.com/gatsbyjs/gatsby">gatsbyjs/gatsby</a></li>
  <li><a href="https://github.com/feathersjs/feathers">feathersjs/feathers</a></li>
  <li><a href="https://github.com/vuejs/vue-cli">vuejs/vue-cli</a></li>
  <li><a href="https://github.com/dvajs/dva">dvajs/dva</a></li>
  <li><a href="https://github.com/umijs/umi">umijs/umi</a></li>
  <li><a href="https://github.com/SBoudrias/Inquirer.js">SBoudrias/Inquirer.js</a></li>
  <li><a href="https://github.com/pedronauck/docz">pedronauck/docz</a></li>
  <li><a href="https://github.com/tasitlabs/tasitsdk">tasitlabs/tasitsdk</a></li>
  <li><a href="https://github.com/zeit/next.js">zeit/next.js</a></li>
  <li><a href="https://github.com/react-bootstrap-table/react-bootstrap-table2">react-bootstrap-table/react-bootstrap-table2</a></li>
  <li><a href="https://github.com/webpack/webpack-cli">webpack/webpack-cli</a></li>
  <li><a href="https://github.com/reakit/reakit">reakit/reakit</a></li>
  <li><a href="https://github.com/webdriverio/webdriverio">webdriverio/webdriverio</a></li>
  <li><a href="https://github.com/graycoreio/daffodil">graycoreio/daffodil</a></li>
  <li><a href="https://github.com/typescript-eslint/typescript-eslint">typescript-eslint/typescript-eslint</a></li>
  <li><a href="https://github.com/stoplightio/prism">stoplightio/prism</a></li>            
</ul>