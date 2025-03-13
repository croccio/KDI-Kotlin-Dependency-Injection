[![Tests](https://github.com/croccio/kdi/actions/workflows/Run%20tests.yml/badge.svg)](https://github.com/croccio/kdi/actions/workflows/Run%20tests.yml)
[![Publish](https://github.com/croccio/kdi/actions/workflows/Publish%20version.yml/badge.svg)](https://github.com/croccio/kdi/actions/workflows/Publish%20version.yml)
[![VERSION](https://jitpack.io/v/croccio/kdi.svg)](https://jitpack.io/#croccio/kdi)
[![MIT](https://img.shields.io/github/license/croccio/kdi)](https://github.com/croccio/KDI-Kotlin-Dependency-Injection/blob/main/LICENSE.txt)

# KDI - Kotlin Dependency Injection 🚀
KDI (Kotlin Dependency Injection) allows you to inject dependencies dynamically, without annotations, and with maximum flexibility.

## 📌 Usage
### 🔹 Defining an Injection
First, create your own module:
```
class MyModule : Module {
    override fun register() {
        // Define your injections here
    }
}
```

Inside the register method, specify the dependencies you want to inject:
```
override fun register() {
    inject(
        Provide { MyClassA() },
        Provide { MyClassB() },
        // Add more dependencies as needed
    )
}
```

### 🔹 Registering Your Module
After defining your module, you need to register it—typically when your app starts:
```
inject(yourModule)
```

Additionally, you can inject instances at runtime:
```
inject(Singleton { yourInstance })
```

### 🔥 Using the Injected Dependencies
To access an injected dependency, use the by injection() delegate:
```
val myInstance: MyClassA by injection()
```

### ⚡ Injection Types
KDI provides multiple ways to inject dependencies:
- Provide → Creates a new instance every time it's injected.
- Singleton → Injects the same instance throughout the application.
- Bind → Maps an interface to a specific implementation.
This makes dependency management in Kotlin simple, flexible, and annotation-free! 🚀
New types will be added soon!