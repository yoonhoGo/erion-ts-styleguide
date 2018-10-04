# Erion TypeScript Style Guide
가치 있는 코드는 이유가 있습니다.

## 목차
1. [변수 이름 명명법](#변수-이름-명명법)
2. [함수](#함수)
3. [클래스와 생성자](#클래스와-생성자)

## 변수 이름 명명법
- 1.1 변수 이름이 예약어를 포함한다면 `_`를 앞에 붙여줍니다.
```typescript
// bad
const oneClass = { /* ... */ }

// good
const _class = { /* ... */ }
```

## 함수
- 2.1 함수 Argument 이름이 예약어를 포함한다면 `_`를 앞에 붙여줍니다.
```typescript
// bad
function setClass(oneClass: Class) { /* ... */ }

// good
function setClass(_class: Class) { /* ... */ }
```

## 클래스와 생성자
- 3.1 `class`내의 `private` 속성은 `__`로 시작합니다.
```typescript
// bad
class Book {
  public author
  private stock
}

// good
class Book {
  public author
  private __stock
}
```

- 3.2 `class`내의 `public` 속성은 `private` 속성 위에 존재해야 합니다.
```typescript
// bad
class Book {
  private __stock
  public author
}

// good
class Book {
  public author
  private __stock
}
``` 