# BunJs란?

## Bun is a JavaScript runtime.
- Bun.Js는 Javascript의 새로운 Runtime입니다.
- Node.js를 대체할 수 있는 Javascript의 Runtime이며, Node에서 작성된 90%의 코드를 돌릴 수 있습니다 !

## 어떤 장점이 있을까요?
- Bun 공식 사이트에서는 다음과 같이 소개하고 있습니다.
### 1. **더 빠른 속도** 
- Bun은 더 빠른 속도로 시작하고 기동합니다.
- Bun은 JavaScriptCore의 확장이며, 이는 Safari를 위한 성능중심의 Javascript 엔진입니다.
- 계산이 극한으로 치달을수록, 이는 더 강하게 나타납니다.
### 2. **우아한 API들** 
- Bun은 Http 서버의 시작이나 파일작성과 같은 흔하게 벌어지는 일들에  최적화된 최소한의 API를 제공합니다. 
### 3. **결합적인 개발자 경험(DX)**
- Bun Js는 JavaScript 앱의 완벽한 도구입니다. 이것은 패키지매니저, 테스트러너, 그리고 번들러를 포함합니다.


- 제가 다른 개발자분들과 얘기를 해보면서 느껴본 Bun.Js의 장점은 아래와 같습니다.	

### 1. **JS,TS의 구분없는 컴파일링**
 - 솔직해지자면, JavaScript를 쓰든 TypeScript를 쓰든, "굳이 그걸로 싸워야하나?"하는 때가 있었다고 생각합니다.
- 요컨데 지금 벌어지고 있는 Delete TypeScript vs Add TypeScript 를 생각해보면, TypeScript vs JavaScript는 결국 코딩의 본질보다는 타입이라는 혓익에만 치우쳐지지 않았는가라고 생각하게 됩니다. 
- 그런데 Bun.js는, TS를 기본적으로 컴파일을 해주니 Ts를 쓰든 Js를 쓰든 _협업을 위한 자세만 갖추어져있다면_ **파편화된 JS개발을 통합** 할 수 있을 것이라고 생각합니다.
### 2. **빠른 속도**
- 패키지 설정이나, 그러한 것들의 속도가 일반적인 NodeJs보다 상당히 빠른것을 체감했었습니다.
- 여러 퍼포먼스에 대한 테스트에서, BunJs는 강력한 성능을 보여왔고, 저는 이 성능에 대한 매력을 느껴서 고를 가치가 있다고 생각합니다!


## 고려해봐야 할 사항
- BunJs는 Linux만 가능합니다!(Window 네이티브는 보안문제로 불가능하지만 노력중이라고 합니다!)
- RunTime에 대한 이해가 필요합니다!

## References
- [Bun.js 공식 사이트](https://bun.sh/)