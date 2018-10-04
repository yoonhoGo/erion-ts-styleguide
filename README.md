# Erion TypeScript Style Guide
쓰여지는 모든 코드는 이유가 있어야 합니다.

## 목차
1. [변수 이름 명명법](#변수-이름-명명법)
2. [함수](#함수)
3. [클래스와 생성자](#클래스와-생성자)

## 변수 이름 명명법
<a name="variable--reserved-word-in-variable"></a>
- [1.1](#variable--reserved-name) 변수 이름이 예약어를 포함한다면 `_`를 앞에 붙여줍니다.
```typescript
// bad
const oneClass = { /* ... */ }

// good
const _class = { /* ... */ }
```

## 함수
<a name="functions--reserved-word-in-argument"></a>
- [2.1](#functions--reserved-word-in-argument) 함수 Argument 이름이 예약어를 포함한다면 `_`를 앞에 붙여줍니다.
```typescript
// bad
function setClass(oneClass: Class) { /* ... */ }

// good
function setClass(_class: Class) { /* ... */ }
```

함수는 동사로 시작해야합니다.
```
// bad
function bookFind() { /* ... */ }

// good
function findBook() { /* ... */ }
```

## 클래스와 생성자
<a name="classes--private-property-underscore"></a>
- [3.1](#classes--private-property-underscore) `class`내의 `private` 속성은 `__`로 시작합니다.
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

<a name="classes--private-property-order"></a>
- [3.2](#classes--private-property-order) `class`내의 `public` 속성은 `private` 속성 위에 존재해야 합니다.
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

`static` 속성은 `class` 제일 위에 존재해야 합니다.
```typescript
// good
class Book {
  static write(): void
  public author
}
```
