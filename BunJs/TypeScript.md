# 타입스크립트
- bun의 빌트인 API를 사용하기 위한 타입스크립트의 정의를 사용하기 위해서는, `bun-types`를 설치해주십시오
```shell
bun add -d bun-types
```
- 그다음, `"bun-types"`를`tsconfig.json`
에 있는 `compilerOptions.types`에 포함시키십시오.

```json
{
  "compilerOptions": {
    "types": ["bun-types"]
  }
}
```
- 이 상태에서, 당신은 타입스크립트 파일이 켜진 상태의 에디터에서 타입스크립트 에러 없이 `bun`의 전역버전을 볼 수 있습니다.

```js
console.log(Bun.version);
```

## 제안되는 `compilerOptions`
- bun은 최상위 레벨에서의 await문이나, JSX, 그리고 확장된 `.ts`의 주입이 가능합니다. 이는 타입스크립트에서는 **절대 허용되지 않던 것 입니다
** 
- 이하는 bun 프로젝트에서 추천하는 `compilerOptions`으로, 이렇게 하여 타입스크립트로부터의 컴파일러 경고없이 그 기능들을 활용할 수 있습니다.

```json

{
  "compilerOptions": {
    // add Bun type definitions 
    // bun의 타입 정의
    "types": ["bun-types"],

    // enable latest features
    // 최신기능 적용
    "lib": ["esnext"],
    "module": "esnext",
    "target": "esnext",

    // if TS 5.x+
    // 타입스크립트 5+
    "moduleResolution": "bundler",
    "noEmit": true,
    "allowImportingTsExtensions": true,
    "moduleDetection": "force",
    // if TS 4.x or earlier 
    // "moduleResolution": "nodenext",

    "jsx": "react-jsx", // support JSX
    "allowJs": true, // allow importing `.js` from `.ts`
    "esModuleInterop": true, // allow default imports for CommonJS modules

    // best practices
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "skipLibCheck": true,
    "composite": true,
    "downlevelIteration": true,
    "allowSyntheticDefaultImports": true
  }
}
```
- 만약 새 디렉토리에서 `bun init` 를 실행하신다면, `tsconfig.json`파일이 당신을 위해 만들어 질 것입니다. 
```shell
bun init
```


## DOM 타입
- 불행히도, `"type"`를 설정한다는 것은, 타입스크립트가 `lib:["dom"]`을 포함한 
 다른 전역타입정의를 무시한다는 의미입니다.
- 만약, 당신이 DOM 타입을 당신의 프로젝트에 추가할 필요성이 있다면, [삼중슬래쉬 지시자](https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html)를 프로젝트의 아무 타입스크립트 파일 최 상단에 넣으십시오.

```ts

/// <reference lib="dom" />
/// <reference lib="dom.iterable" />

```
## References
https://bun.sh/docs/typescript