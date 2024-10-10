# next-fsd
Feature-Sliced Design pattern example

- 기존에 사용하던 구조에 FSD 적용 (기존 구조 참고 : https://github.com/jjuya/jenkins-docker-setting)

# 구조
> Public API를 사용하여 외부에서 불필요한 슬라이스와 세그먼트 고립
> 내부에서는 접근 가능하지만 외부에서는 불가능하도록

```shell
├── pages # NextJS pages 폴더
├── src
    ├── entities
    ├── features
    ├── layout # FSD app 폴더
    ├── shared
    ├── views # FSD pages 폴더
    ├── widgets
```

### /pages
- 엡 진입 포인트

### /src/layout
- Provider, 라우터, 전역 스타일, 전역 타입 등이 정의

### /src/views
- 앱의 페이지들을 포함하고 있는 레이어

### widgets
- 페이지에서 사용하는 standalone UI 컴포넌트

### features
- 비지니스 가치를 지닌 유저 시나리오와 기능에 관한 것들이 포함된 레이어
- 옵셔널 레이어
- 예시 : 리뷰 작성, 별점 주기 등

### entities
- 비지니스 개체(예시 : 유저, 리뷰, 댓글 등)
- 옵셔널 레이어

### shared
- 범용적으로 사용되는 재사용가능한 컴포넌트와 유틸리티를 포함하는 레이어
- UI 키트, axios 설정, 앱 설정, 비지니스 로직에 묶여있지 않은 각종 헬퍼 등