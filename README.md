# revisiting-patterns

Quickly brush up on basic design patterns

## Creational:

|     | **Pattern**      | **When to use?**                                                                                                        | **Example** |
| --- | ---------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------- |
| 🏠  | Simple Factory   | When you want to hide object creation details and not repeat same code                                                  | [TS][1]     |
| 🏭  | Factory Method   | When you want to abstract the process of object generation so that the type of the object can be determined at run-time | [TS][2]     |
|     | Abstract Factory | Creates an instance of several families of classes                                                                      | [TS](#)     |
|     | Builder          | Separates object construction from its representation                                                                   | [TS](#)     |
|     | Prototype        | A fully initialized instance to be copied or cloned                                                                     | [TS](#)     |
|     | Singleton        | A class of which only a single instance can exist                                                                       | [TS](#)     |

## Structural:

|     | **Pattern** | **When to use?**                                        | **Example** |
| --- | ----------- | ------------------------------------------------------- | ----------- |
|     | Adapter     | Match interfaces of different classes                   | [TS](#)     |
|     | Bridge      | Separates an object’s interface from its implementation | [TS](#)     |
|     | Composite   | A tree structure of simple and composite objects        | [TS](#)     |
|     | Decorator   | Add responsibilities to objects dynamically             | [TS](#)     |
|     | Facade      | A single class that represents an entire subsystem      | [TS](#)     |
|     | Flyweight   | A fine-grained instance used for efficient sharing      | [TS](#)     |
|     | Proxy       | An object representing another object                   | [TS](#)     |

## Behavioral:

|     | **Pattern**     | **When to use?**                                      | **Example** |
| --- | --------------- | ----------------------------------------------------- | ----------- |
|     | Chain of Resp.  | A way of passing a request between a chain of objects | [TS](#)     |
|     | Command         | Encapsulate a command request as an object            | [TS](#)     |
|     | Interpreter     | A way to include language elements in a program       | [TS](#)     |
|     | Iterator        | Sequentially access the elements of a collection      | [TS](#)     |
|     | Mediator        | Defines simplified communication between classes      | [TS](#)     |
|     | Memento         | Capture and restore an object's internal state        | [TS](#)     |
|     | Observer        | A way of notifying change to a number of classes      | [TS](#)     |
|     | State           | Alter an object's behavior when its state changes     | [TS](#)     |
|     | Strategy        | Encapsulates an algorithm inside a class              | [TS](#)     |
|     | Template Method | Defer the exact steps of an algorithm to a subclass   | [TS](#)     |
|     | Visitor         | Defines a new operation to a class without change     | [TS](#)     |

[1]: https://www.typescriptlang.org/play/#src=%2F**%0D%0A%20*%20Real%20world%20example%3A%0D%0A%20*%20%0D%0A%20*%20Consider%2C%20you%20are%20building%20a%20house%20and%20you%20need%20doors.%20%0D%0A%20*%20You%20can%20either%20put%20on%20your%20carpenter%20clothes%2C%20%0D%0A%20*%20bring%20some%20wood%2C%20glue%2C%20nails%20and%20all%20the%20tools%20required%20%0D%0A%20*%20to%20build%20the%20door%20and%20start%20building%20it%20in%20your%20house%20%0D%0A%20*%20or%20you%20can%20simply%20call%20the%20factory%20and%20get%20the%20built%20%0D%0A%20*%20door%20delivered%20to%20you%20so%20that%20you%20don't%20need%20to%20learn%20%0D%0A%20*%20anything%20about%20the%20door%20making%20or%20to%20deal%20with%20the%20%0D%0A%20*%20mess%20that%20comes%20with%20making%20it.%0D%0A%20*%20*%2F%0D%0A%0D%0Ainterface%20IDoor%20%7B%0D%0A%20%20%20%20getWidth%3A%20()%20%3D%3E%20number%0D%0A%20%20%20%20getHeight%3A%20()%20%3D%3E%20number%0D%0A%7D%0D%0A%0D%0Aclass%20WoodenDoor%20implements%20IDoor%20%7B%0D%0A%20%20%20%20constructor(protected%20width%3A%20number%2C%20protected%20height%3A%20number)%20%7B%0D%0A%20%20%20%20%20%20%20%20this.width%20%3D%20width%0D%0A%20%20%20%20%20%20%20%20this.height%20%3D%20height%0D%0A%20%20%20%20%7D%0D%0A%0D%0A%20%20%20%20getWidth%20%3D%20()%20%3D%3E%20this.width%0D%0A%0D%0A%20%20%20%20getHeight%20%3D%20()%20%3D%3E%20this.height%0D%0A%7D%0D%0A%0D%0Aclass%20DoorFactory%20%7B%0D%0A%20%20%20%20makeDoor%20%3D%20(width%3A%20number%2C%20height%3A%20number)%20%3D%3E%20new%20WoodenDoor(width%2C%20height)%20%0D%0A%7D%0D%0A%0D%0A%2F%2F%20Test%0D%0A%0D%0Afunction%20test()%20%7B%0D%0A%20%20%20%20const%20factory%20%3D%20new%20DoorFactory()%0D%0A%20%20%20%20const%20door%20%3D%20factory.makeDoor(10%2C%2012)%0D%0A%20%20%20%20console.log(door)%0D%0A%7D%0D%0A%0D%0Atest()%0D%0A
[2]: https://www.typescriptlang.org/play/#src=%2F**%0D%0A%20*%20Real%20world%20example%3A%0D%0A%20*%20%0D%0A%20*%20Consider%2C%20you%20want%20to%20display%20currency%20code%20based%20on%20%0D%0A%20*%20a%20given%20country%20%0D%0A%20*%20*%2F%0D%0A%0D%0Ainterface%20ICurrency%20%7B%0D%0A%20%20%20%20code%3A%20()%20%3D%3E%20string%0D%0A%7D%0D%0A%0D%0Aclass%20Euro%20implements%20ICurrency%20%7B%0D%0A%20%20%20code%20%3D%20()%20%3D%3E%20'EUR'%0D%0A%7D%0D%0A%0D%0Aclass%20USD%20implements%20ICurrency%20%7B%0D%0A%20%20%20code%20%3D%20()%20%3D%3E%20'USD'%0D%0A%7D%0D%0A%0D%0Atype%20country%20%3D%20'Spain'%20%7C%20'France'%20%7C%20'USA'%20%0D%0A%0D%0Aabstract%20class%20Currency%20%7B%0D%0A%20%20%20%20%2F%2F%20factory%20method%0D%0A%20%20%20%20protected%20abstract%20currency()%3A%20ICurrency%0D%0A%20%20%20%20getCode%20%3D%20()%20%3D%3E%20this.currency().code()%0D%0A%7D%0D%0A%0D%0Aclass%20EuropeanCurrency%20extends%20Currency%20%7B%0D%0A%20%20%20%20protected%20currency%20%3D%20()%3A%20ICurrency%20%3D%3E%20new%20Euro()%0D%0A%7D%0D%0A%0D%0Aclass%20AmericanCurrency%20extends%20Currency%20%7B%0D%0A%20%20%20%20protected%20currency%20%3D%20()%3A%20ICurrency%20%3D%3E%20new%20USD()%0D%0A%7D%0D%0A%0D%0Aclass%20CurrencyFactory%20%7B%0D%0A%20%20%20%20displayCurrencyCode%20%3D%20(c%3A%20country)%3A%20string%20%3D%3E%20%7B%0D%0A%20%20%20%20%20%20%20%20switch%20(c)%20%7B%0D%0A%20%20%20%20%20%20%20%20%20%20%20%20case%20'Spain'%20%7C%7C%20'France'%3A%20return%20new%20EuropeanCurrency().getCode()%0D%0A%20%20%20%20%20%20%20%20%20%20%20%20case%20'USA'%3A%20return%20new%20AmericanCurrency().getCode()%0D%0A%20%20%20%20%20%20%20%20%20%20%20%20default%3A%20throw%20new%20Error('Invalid%20country')%0D%0A%20%20%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%7D%0D%0A%7D%0D%0A%0D%0A%2F%2F%20Test%0D%0A%0D%0Afunction%20test()%20%7B%0D%0A%20%20%20%20const%20factory%20%3D%20new%20CurrencyFactory()%0D%0A%20%20%20%20const%20code%20%3D%20factory.displayCurrencyCode('USA')%0D%0A%20%20%20%20console.log(code)%0D%0A%7D%0D%0A%0D%0Atest()%0D%0A

## References

1. [Design patterns for Humans](https://github.com/kamranahmedse/design-patterns-for-humans)
2. [Design patterns in Swift](https://github.com/ochococo/Design-Patterns-In-Swift)
3. [DoFactory .net Design Patterns](https://www.dofactory.com/net/design-patterns)
