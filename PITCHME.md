---?image=template/img/pencils.jpg
@title[Split-Screen Templates]

## @color[black](《重构》)
#### @color[black](——读书笔记)

---?color=white

@quote[在不改变代码外在行为的前提下，对代码做出修改，以改进程序的内部结构](Martin Fowler)

---?image=template/img/bg/black.jpg&position=right&size=50% 100%
@title[Heading + List Body]

@snap[west split-screen-heading text-black span-50]
Why
@snapend

@snap[east text-white span-45]
@ol[split-screen-list](false)
- 改进程序设计
- 使程序更容易理解
- 帮助找到 bug
- 提高编程速度
@olend
@snapend

---?image=template/img/bg/black.jpg&position=right&size=50% 100%
@title[Heading + List Body]

@snap[west split-screen-heading text-black span-50]
When
@snapend

@snap[east text-white span-45]
@ol[split-screen-list](false)
- 添加功能时
- 修复bug时
- 代码复审时
@olend
@snapend

---?image=template/img/bg/black.jpg&position=left&size=50% 100%
@title[Heading + List Body]

@snap[east split-screen-heading text-orange span-50]
要点
@snapend

@snap[west text-white span-65]
@ol[split-screen-list](false)
- 添加新功能
- 性能
@olend
@snapend


---?image=template/img/bg/black.jpg&position=right&size=50% 100%
@title[Heading + List Body]

@snap[west split-screen-heading text-black span-50]
How
@snapend

@snap[east text-white span-45]
测试、小修改、<br>测试、小修改
@snapend

---?image=template/img/bg/black.jpg&position=left&size=50% 100%
@title[Heading + List Body]

@snap[east split-screen-heading text-orange span-50]
搭建<br>测试环境
@snapend

@snap[west text-white span-65]
@ol[split-screen-list](false)
- 确保独立可靠
- 确保完全自动化
- 在开始编程前写测试代码
@olend
@snapend


---?image=template/img/bg/black.jpg&position=left&size=50% 100%
@title[Heading + List Body]

@snap[east split-screen-heading text-orange span-50]
找出<br>"坏味道"
@snapend

@snap[west text-white span-65]
@ol[split-screen-list](false)
- 重复代码
- 过长函数
- switch 表达式
- 临时字段
- ...
@olend
@snapend

---?image=template/img/bg/black.jpg&position=right&size=50% 100%
@title[Text + Image]

@snap[west split-screen-heading text-black]
开始重构
@snapend

@snap[east split-screen-img]
![DEVELOPER](template/img/developer.jpg)
@snapend

---?color=white
@title[Fenced Code Block]

#### 提炼函数

```java
void print(double amount) {
    printBanner();

    printDetail(amount);
    // System.out.println("haha");
    // System.out.println("amount: " amount);
  }

  void printDetail(double amount) {
    System.out.println("haha");
    System.out.println("amount: " + amount);
  }
```

---?color=white
@title[Fenced Code Block]

#### 以查询取代临时变量

```java
  // double basePrice = quantity * itemPrice;

  if (basePrice() > 100) {
    return basePrice() * 0.95;
  } else {
    return basePrice() * 0.98;
  }

  double basePrice(){
    return quantity * itemPrice;
  }
```

---?color=white
@title[Fenced Code Block]

#### 搬移函数

![MOVE-METHOD](template/img/refactoring/move-method.png)

---?color=white
@title[Fenced Code Block]

#### 以多态取代条件表达式
#### 以 State/Strategy 取代类型码

```java
 int getCharge() {
    switch (type) {
      case CHILDENS:
        return daysRented * 2;
      case REGULAR:
        return daysRented * 1.5;
      default:
        return 0;
    }
  }
```


---?color=white
@title[Fenced Code Block]

![STATE](template/img/refactoring/state.png)

---?image=template/img/bg/black.jpg&position=right&size=50% 100%
@title[Text + Image]

@snap[west split-screen-heading text-orange]
赞美太阳！
@snapend

@snap[east split-screen-img]
![DEVELOPER](template/img/developer.jpg)
@snapend