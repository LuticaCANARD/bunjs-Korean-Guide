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
- bun은 최상위 레벨에서의 await문이나, JSX, 그리고 확장된 `.ts`의 주입이 가능합니다. 이는 타입스크립트 

## References
https://bun.sh/docs/typescript