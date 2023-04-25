## 引

在 ts 中 interface 可以表示具体的一种数据结构，但当我们需要将 interface 转换成 class 时，直接使用 interface 的话，会导致一些问题，比如 interface 中的属性无法被继承，所以我们需要将 interface 转换成 class，这里介绍一种方法。

## 例

### 数据结构

```typescript
interface IPerson {
  name: string;
  age: number;
}

class Person implements IPerson {
  name: string;
  age: number;
  getName(): string {
    return this.name;
  }
}
```

### 问题

当我们直接从网络获取到一份 json 的 string 时候，我们需要将其转换成对应的数据结构，这里我们使用`JSON.parse`来将其转换成`Person`，但是直接调用 getName 方法是会报错的，因为`JSON.parse`返回的是一个`IPerson`，而不是`Person`，所以我们需要将其转换成`Person`。

```typescript
//即使使用了类型断言，也是不行的
const person: Person = JSON.parse(jsonString);
person.getName(); // 报错
```

### 解决

我们可以使用`Object.assign`来将`IPerson`转换成`Person`

```typescript
const person: IPerson = JSON.parse(jsonString);
const person2: Person = Object.assign(new Person(), person);
person2.getName(); // 正常
```
