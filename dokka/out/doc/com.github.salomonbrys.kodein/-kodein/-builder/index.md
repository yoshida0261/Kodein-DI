[com.github.salomonbrys.kodein](../../index.md) / [Kodein](../index.md) / [Builder](.)

# Builder

`class Builder`

Allows for the DSL inside the block argument of the constructor of `Kodein` and `Kodein.Module`.

Methods of this classes are really just proxies to the [TBuilder](-t-builder/index.md) or [KodeinContainer.Builder](../../-kodein-container/-builder/index.md) methods.

### Types

| Name | Summary |
|---|---|
| [ConstantBinder](-constant-binder/index.md) | `inner class ConstantBinder`<br>Left part of the constant-binding syntax (`constant(tag)`). |
| [TBuilder](-t-builder/index.md) | `inner class TBuilder`<br>Class holding all typed API (meaning the API where you provide [Type](http://docs.oracle.com/javase/6/docs/api/java/lang/reflect/Type.html), [TypeToken](../../-type-token/index.md) or `Class` objects). |

### Properties

| Name | Summary |
|---|---|
| [container](container.md) | `val container: `[`Builder`](../../-kodein-container/-builder/index.md)<br>Every methods, either in this or in [TBuilder](-t-builder/index.md) eventually ends up to a call to this builder. |
| [typed](typed.md) | `val typed: `[`TBuilder`](-t-builder/index.md)<br>Allows to access all typed API (meaning the API where you provide [Type](http://docs.oracle.com/javase/6/docs/api/java/lang/reflect/Type.html), [TypeToken](../../-type-token/index.md) or `Class` objects). |

### Functions

| Name | Summary |
|---|---|
| [bindDirect](bind-direct.md) | `fun bindDirect(tag: Any? = null, overrides: Boolean? = null): `[`DirectBinder`](-t-builder/-direct-binder/index.md)<br>Starts a direct binding with a given tag. A direct bind does not define the type to be bound, the type will be defined according to the bound factory. |
| [bindErased](bind-erased.md) | `fun <T : Any> bindErased(tag: Any? = null, overrides: Boolean? = null): `[`TypeBinder`](-t-builder/-type-binder/index.md)`<T>`<br>Starts the binding of a given type with a given tag. |
| [bindGeneric](bind-generic.md) | `fun <T : Any> bindGeneric(tag: Any? = null, overrides: Boolean? = null): `[`TypeBinder`](-t-builder/-type-binder/index.md)`<T>`<br>Starts the binding of a given type with a given tag. |
| [constant](constant.md) | `fun constant(tag: Any, overrides: Boolean? = null): `[`ConstantBinder`](-constant-binder/index.md)<br>Starts a constant binding. |
| [extend](extend.md) | `fun extend(kodein: `[`Kodein`](../index.md)`, allowOverride: Boolean = false): Unit`<br>Imports all bindings defined in the given [Kodein](../index.md) into this builder. |
| [import](import.md) | `fun import(module: `[`Module`](../-module/index.md)`, allowOverride: Boolean = false): Unit`<br>Imports all bindings defined in the given [Kodein.Module](../-module/index.md) into this builders definition. |
| [onReady](on-ready.md) | `fun onReady(cb: `[`Kodein`](../index.md)`.() -> Unit): Unit`<br>Adds a callback that will be called once the Kodein object is configured and instantiated. |

### Extension Functions

| Name | Summary |
|---|---|
| [activitySingleton](../../../com.github.salomonbrys.kodein.android/activity-singleton.md) | `fun <T : Any> Builder.~~activitySingleton~~(creator: `[`Kodein`](../index.md)`.(Activity) -> T): `[`Factory`](../../-factory/index.md)`<Activity, T>`<br>Creates an activity scoped singleton factory, effectively a `factory { Activity -> T }`. |
| [autoActivitySingleton](../../../com.github.salomonbrys.kodein.android/auto-activity-singleton.md) | `fun <T : Any> Builder.~~autoActivitySingleton~~(creator: `[`Kodein`](../index.md)`.(Activity) -> T): `[`Factory`](../../-factory/index.md)`<Unit, T>`<br>Creates an activity auto-scoped singleton factory, effectively a `provider { -> T }`. |
| [autoScopedSingleton](../../auto-scoped-singleton.md) | `fun <C, T : Any> Builder.autoScopedSingleton(scope: `[`AutoScope`](../../-auto-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CAutoScopedSingleton`](../../-c-auto-scoped-singleton/index.md)`<C, T>`<br>Creates an auto-scoped singleton provider, effectively a `provider { -> T }`. |
| [autoScopedSingleton](../../../com.github.salomonbrys.kodein.erased/auto-scoped-singleton.md) | `fun <C, T : Any> Builder.autoScopedSingleton(scope: `[`AutoScope`](../../-auto-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CAutoScopedSingleton`](../../-c-auto-scoped-singleton/index.md)`<C, T>`<br>Creates an auto-scoped singleton provider, effectively a `provider { -> T }`. |
| [bind](../../bind.md) | `fun Builder.bind(tag: Any? = null, overrides: Boolean? = null): `[`DirectBinder`](-t-builder/-direct-binder/index.md)<br>Starts a direct binding with a given tag. A direct bind does not define the type to be bound, the type will be defined according to the bound factory. |
| [bind](../../../com.github.salomonbrys.kodein.erased/bind.md) | `fun Builder.bind(tag: Any? = null, overrides: Boolean? = null): `[`DirectBinder`](-t-builder/-direct-binder/index.md)<br>Starts a direct binding with a given tag. A direct bind does not define the type to be bound, the type will be defined according to the bound factory. |
| [broadcastReceiverSingleton](../../../com.github.salomonbrys.kodein.android/broadcast-receiver-singleton.md) | `fun <T : Any> Builder.~~broadcastReceiverSingleton~~(creator: `[`Kodein`](../index.md)`.(BroadcastReceiver) -> T): `[`Factory`](../../-factory/index.md)`<BroadcastReceiver, T>`<br>Creates a broadcast receiver scoped singleton factory, effectively a `factory { BroadcastReceiver -> T }`. |
| [contextSingleton](../../../com.github.salomonbrys.kodein.android/context-singleton.md) | `fun <T : Any> Builder.~~contextSingleton~~(creator: `[`Kodein`](../index.md)`.(Context) -> T): `[`Factory`](../../-factory/index.md)`<Context, T>`<br>Creates a context scoped singleton factory, effectively a `factory { Context -> T }`. |
| [eagerSingleton](../../eager-singleton.md) | `fun <T : Any> Builder.eagerSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates an eager singleton: will create an instance as soon as kodein is ready (all bindings are set) and will always return this instance. |
| [eagerSingleton](../../../com.github.salomonbrys.kodein.erased/eager-singleton.md) | `fun <T : Any> Builder.eagerSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates an eager singleton: will create an instance as soon as kodein is ready (all bindings are set) and will always return this instance. |
| [erasedAutoScopedSingleton](../../erased-auto-scoped-singleton.md) | `fun <C, T : Any> Builder.erasedAutoScopedSingleton(scope: `[`AutoScope`](../../-auto-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CAutoScopedSingleton`](../../-c-auto-scoped-singleton/index.md)`<C, T>`<br>Creates an auto-scoped singleton provider, effectively a `provider { -> T }`. |
| [erasedEagerSingleton](../../erased-eager-singleton.md) | `fun <T : Any> Builder.erasedEagerSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates an eager singleton: will create an instance as soon as kodein is ready (all bindings are set) and will always return this instance. |
| [erasedFactory](../../erased-factory.md) | `fun <A, T : Any> Builder.erasedFactory(creator: `[`Kodein`](../index.md)`.(A) -> T): `[`CFactory`](../../-c-factory/index.md)`<A, T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../erased-factory.md#com.github.salomonbrys.kodein$erasedFactory(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function2((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.erasedFactory.A, com.github.salomonbrys.kodein.erasedFactory.T)))/creator) function will be called. |
| [erasedInstance](../../erased-instance.md) | `fun <T : Any> Builder.erasedInstance(instance: T): `[`CInstance`](../../-c-instance/index.md)`<T>`<br>Creates an instance provider: will always return the given instance. |
| [erasedProvider](../../erased-provider.md) | `fun <T : Any> Builder.erasedProvider(creator: `[`Kodein`](../index.md)`.() -> T): `[`CProvider`](../../-c-provider/index.md)`<T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../erased-provider.md#com.github.salomonbrys.kodein$erasedProvider(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function1((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.erasedProvider.T)))/creator) function will be called. |
| [erasedScopedSingleton](../../erased-scoped-singleton.md) | `fun <C, T : Any> Builder.erasedScopedSingleton(scope: `[`Scope`](../../-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CScopedSingleton`](../../-c-scoped-singleton/index.md)`<C, T>`<br>Creates a scoped singleton factory, effectively a `factory { Scope -> T }`. |
| [erasedSingleton](../../erased-singleton.md) | `fun <T : Any> Builder.erasedSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a singleton: will create an instance on first request and will subsequently always return the same instance. |
| [erasedThreadSingleton](../../erased-thread-singleton.md) | `fun <T : Any> Builder.erasedThreadSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a thread singleton: will create an instance on first request per thread and will subsequently always return the same instance for this thread. |
| [factory](../../factory.md) | `fun <A, T : Any> Builder.factory(creator: `[`Kodein`](../index.md)`.(A) -> T): `[`CFactory`](../../-c-factory/index.md)`<A, T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../factory.md#com.github.salomonbrys.kodein$factory(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function2((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.factory.A, com.github.salomonbrys.kodein.factory.T)))/creator) function will be called. |
| [factory](../../../com.github.salomonbrys.kodein.erased/factory.md) | `fun <A, T : Any> Builder.factory(creator: `[`Kodein`](../index.md)`.(A) -> T): `[`CFactory`](../../-c-factory/index.md)`<A, T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../../com.github.salomonbrys.kodein.erased/factory.md#com.github.salomonbrys.kodein.erased$factory(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function2((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.erased.factory.A, com.github.salomonbrys.kodein.erased.factory.T)))/creator) function will be called. |
| [fragmentSingleton](../../../com.github.salomonbrys.kodein.android/fragment-singleton.md) | `fun <T : Any> Builder.~~fragmentSingleton~~(creator: `[`Kodein`](../index.md)`.(Fragment) -> T): `[`Factory`](../../-factory/index.md)`<Fragment, T>`<br>Creates a fragment scoped singleton factory, effectively a `factory { Fragment -> T }`. |
| [genericAutoScopedSingleton](../../generic-auto-scoped-singleton.md) | `fun <C, T : Any> Builder.genericAutoScopedSingleton(scope: `[`AutoScope`](../../-auto-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CAutoScopedSingleton`](../../-c-auto-scoped-singleton/index.md)`<C, T>`<br>Creates an auto-scoped singleton provider, effectively a `provider { -> T }`. |
| [genericEagerSingleton](../../generic-eager-singleton.md) | `fun <T : Any> Builder.genericEagerSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates an eager singleton: will create an instance as soon as kodein is ready (all bindings are set) and will always return this instance. |
| [genericFactory](../../generic-factory.md) | `fun <A, T : Any> Builder.genericFactory(creator: `[`Kodein`](../index.md)`.(A) -> T): `[`CFactory`](../../-c-factory/index.md)`<A, T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../generic-factory.md#com.github.salomonbrys.kodein$genericFactory(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function2((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.genericFactory.A, com.github.salomonbrys.kodein.genericFactory.T)))/creator) function will be called. |
| [genericInstance](../../generic-instance.md) | `fun <T : Any> Builder.genericInstance(instance: T): `[`CInstance`](../../-c-instance/index.md)`<T>`<br>Creates an instance provider: will always return the given instance. |
| [genericProvider](../../generic-provider.md) | `fun <T : Any> Builder.genericProvider(creator: `[`Kodein`](../index.md)`.() -> T): `[`CProvider`](../../-c-provider/index.md)`<T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../generic-provider.md#com.github.salomonbrys.kodein$genericProvider(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function1((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.genericProvider.T)))/creator) function will be called. |
| [genericScopedSingleton](../../generic-scoped-singleton.md) | `fun <C, T : Any> Builder.genericScopedSingleton(scope: `[`Scope`](../../-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CScopedSingleton`](../../-c-scoped-singleton/index.md)`<C, T>`<br>Creates a scoped singleton factory, effectively a `factory { Scope -> T }`. |
| [genericSingleton](../../generic-singleton.md) | `fun <T : Any> Builder.genericSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a singleton: will create an instance on first request and will subsequently always return the same instance. |
| [genericThreadSingleton](../../generic-thread-singleton.md) | `fun <T : Any> Builder.genericThreadSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a thread singleton: will create an instance on first request per thread and will subsequently always return the same instance for this thread. |
| [instance](../../instance.md) | `fun <T : Any> Builder.instance(instance: T): `[`CInstance`](../../-c-instance/index.md)`<T>`<br>Creates an instance provider: will always return the given instance. |
| [instance](../../../com.github.salomonbrys.kodein.erased/instance.md) | `fun <T : Any> Builder.instance(instance: T): `[`CInstance`](../../-c-instance/index.md)`<T>`<br>Creates an instance provider: will always return the given instance. |
| [provider](../../provider.md) | `fun <T : Any> Builder.provider(creator: `[`Kodein`](../index.md)`.() -> T): `[`CProvider`](../../-c-provider/index.md)`<T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../provider.md#com.github.salomonbrys.kodein$provider(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function1((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.provider.T)))/creator) function will be called. |
| [provider](../../../com.github.salomonbrys.kodein.erased/provider.md) | `fun <T : Any> Builder.provider(creator: `[`Kodein`](../index.md)`.() -> T): `[`CProvider`](../../-c-provider/index.md)`<T>`<br>Creates a factory: each time an instance is needed, the function [creator](../../../com.github.salomonbrys.kodein.erased/provider.md#com.github.salomonbrys.kodein.erased$provider(com.github.salomonbrys.kodein.Kodein.Builder, kotlin.Function1((com.github.salomonbrys.kodein.Kodein, com.github.salomonbrys.kodein.erased.provider.T)))/creator) function will be called. |
| [scopedSingleton](../../scoped-singleton.md) | `fun <C, T : Any> Builder.scopedSingleton(scope: `[`Scope`](../../-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CScopedSingleton`](../../-c-scoped-singleton/index.md)`<C, T>`<br>Creates a scoped singleton factory, effectively a `factory { Scope -> T }`. |
| [scopedSingleton](../../../com.github.salomonbrys.kodein.erased/scoped-singleton.md) | `fun <C, T : Any> Builder.scopedSingleton(scope: `[`Scope`](../../-scope/index.md)`<C>, creator: `[`Kodein`](../index.md)`.(C) -> T): `[`CScopedSingleton`](../../-c-scoped-singleton/index.md)`<C, T>`<br>Creates a scoped singleton factory, effectively a `factory { Scope -> T }`. |
| [serviceSingleton](../../../com.github.salomonbrys.kodein.android/service-singleton.md) | `fun <T : Any> Builder.~~serviceSingleton~~(creator: `[`Kodein`](../index.md)`.(Service) -> T): `[`Factory`](../../-factory/index.md)`<Service, T>`<br>Creates a service scoped singleton factory, effectively a `factory { Service -> T }`. |
| [singleton](../../singleton.md) | `fun <T : Any> Builder.singleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a singleton: will create an instance on first request and will subsequently always return the same instance. |
| [singleton](../../../com.github.salomonbrys.kodein.erased/singleton.md) | `fun <T : Any> Builder.singleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a singleton: will create an instance on first request and will subsequently always return the same instance. |
| [supportFragmentSingleton](../../../com.github.salomonbrys.kodein.android/support-fragment-singleton.md) | `fun <T : Any> Builder.~~supportFragmentSingleton~~(creator: `[`Kodein`](../index.md)`.(Fragment) -> T): `[`Factory`](../../-factory/index.md)`<Fragment, T>`<br>Creates a support fragment scoped singleton factory, effectively a `factory { Fragment -> T }`. |
| [threadSingleton](../../thread-singleton.md) | `fun <T : Any> Builder.threadSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a thread singleton: will create an instance on first request per thread and will subsequently always return the same instance for this thread. |
| [threadSingleton](../../../com.github.salomonbrys.kodein.erased/thread-singleton.md) | `fun <T : Any> Builder.threadSingleton(creator: `[`Kodein`](../index.md)`.() -> T): `[`AProvider`](../../-a-provider/index.md)`<T>`<br>Creates a thread singleton: will create an instance on first request per thread and will subsequently always return the same instance for this thread. |