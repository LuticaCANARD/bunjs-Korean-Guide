# Lockfile
- `bun install`의 실행은 `bun.lockb`이라고 불리는 이진파일을 만들게 됩니다.

### 왜 이진파일인가요?
- 간단히 말하자면, 성능때문입니다.
- bun의 lockfile은 엄청나게 빠르게 저장하고 불러오며, 그리고 lockfiles 안에 일반적으로 들어가는것 보다 수많은 데이터를 저장할 수 있습니다.
 
### 어떻게하면 bun의 lockfile을 관측할 수 있나요?
- `bun install -y`의 실행은 좀더 쉽게 관측가능한 yarn 과의 비교가 가능한 `yarn.lock`을 생성합니다.

### 어떻게 `git diff`를 bun의 lockfile에 적용하나요?
- `.gitattributes`파일에 이하를 추가하십시오.
```
*.lockb binary diff=lockb
```

- 그 다음, git의 지역설정으로 이하를 추가합니다.

 ```shell
git config diff.lockb.textconv bun
git config diff.lockb.binary true

 ```

- 혹은 이하를 통해 시스템 전체의 `--global`옵션을 추가할 수 있습니다.
```shell
git config --global diff.lockb.textconv bun
git config --global diff.lockb.binary true
```

## 이것은 어떻게 작동하나요 :

- `textconv`는 git에게 차이점 비교 이전에 bun을 실행하게 합니다
- `binary`는 git에게 파일을 이진으로 처리하게끔 합니다. (그러므로, 이는 line by line으로 비교하게 시도하지 않습니다.)
- lockfile위의 bun을 실행하면, 사람이 읽을 수 있는 diff로 출력됩니다. 그러므로, 우리는 그저 git이 차이점 비교 이전에 lockfile을 bun위에서 실행하게 하면 될 뿐입니다.


Can I opt out?
## 어떻게 다룰수있을까요?
- lockfile없이 만들고싶다면:
```
bun install --no-save
```
- yarn lockfile을 bun.lockb.외에 추가적으로 설치하고싶다면

```CLI flag
bunfig.toml
bun install --yarn
```