# typescript： 类中的private 和 protected

## private: 私有成员    

### typescript 与 es6 private 的区别：
-   es6的类暂时不支持protected修饰

### typescript 中的 private
-   经过 private 修饰后的属性只能通过类本身访问， 在类的外部、实例、子类中都无法访问

-   例子：

    ```
        class Animal {
            private name: string
            constructor(name: string) {
                this.name = name
            }
        }

        class Dog extends Animal {
            constructor(name: string) {
                super(name)
            }

            printName() {
                // 报错， 不能访问
                console.log(this.name)
            }
        }

        let dog = new Dog('huahua')

        console.log(dog.name) // 报错， 不能访问
    ```




## protected：受保护成员

### typescript 与 es6 protected 的区别：
- es6的类暂时不支持protected修饰

### typescript 中的 protected
-   经过 protected修饰后的属性仅能通过类本身或者类的子类访问
-   tip：若想保证类的抽象化（不能通过new 实例化），-------> protected constructor()

-   例子：

    ```
        class Animal {
            protected name: string
            constructor(name: string) {
                this.name = name
            }
        }

        class Dog extends Animal {
            constructor(name: string) {
                super(name)
            }

            printName () {
                console.log(this.name)
            }
        }

        let dog = new Dog('huahua')
        dog.printName() // 'huahua'
        dog.name // 报错， 不能访问
    
    ```


    