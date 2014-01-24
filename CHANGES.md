# Changelog

## 2.22 - 2.23 (2014-01-25)

* ([6446704](https://github.com/EsotericSoftware/kryo/commit/6446704b905944735a9f719154c8ae9812883563)) Add changes
* ([b0bae96](https://github.com/EsotericSoftware/kryo/commit/b0bae96d7cdc6a00e087ebca6b155699ba2d064f)) Fix setStreamFactory to accept StreamFactory instead of FastestStreamFactory
* ([323dc6f](https://github.com/EsotericSoftware/kryo/commit/323dc6f13a9f6e78ed1a6d6d5c5b50f72f35be96)) Allow to override type by name lookup in DefaultClassResolver.
* ([7576ed3](https://github.com/EsotericSoftware/kryo/commit/7576ed3f35727911410bdaa9d63966e056edea56)) Reduce visibility of FieldSerializer’s internal helper classes, make them package private
* ([0fcc93c](https://github.com/EsotericSoftware/kryo/commit/0fcc93c0a9d399236918e896372da452a5eb9482)) Fix an NPE
* ([f2fc9ff](https://github.com/EsotericSoftware/kryo/commit/f2fc9ff04c29a5e4fd7d25d062f4048e07ca9212)) Javadoc
* ([45c8920](https://github.com/EsotericSoftware/kryo/commit/45c8920d987deb1386ce6c087ec6fd3073b751a0)) Avoid idToRegistration for NAME.
* ([82d134d](https://github.com/EsotericSoftware/kryo/commit/82d134d5ab91918c70290289a9bafe1efeabf60b)) Fixes #168
* ([8daf628](https://github.com/EsotericSoftware/kryo/commit/8daf6280706df23eef21ce8403ecf8122ce98560)) Update to DateSerializer and new LocaleSerializer
* ([9f7fb4d](https://github.com/EsotericSoftware/kryo/commit/9f7fb4d66e1293cf661c90b15da60ce3eec73c13)) Added default serializer for java.util.Locale
* ([de925f5](https://github.com/EsotericSoftware/kryo/commit/de925f57b070a6ffcb7dc9f2718e6debece8163e)) Update to DateSerializer and new LocaleSerializer
* ([faf05e0](https://github.com/EsotericSoftware/kryo/commit/faf05e0db69ef65bee741943bda1b83c3c46f197)) Fixed issue #161
* ([9f0bfa7](https://github.com/EsotericSoftware/kryo/commit/9f0bfa7e7a81e34ef536e5c6ae263538eaf944b7)) Add a possibility to set a custom InstantiationStrategy. The Kryo.DefaultInstantiatorStrategy implements the usual Kryo behavior, where it tries to invoke a no-arg constructor when it needs to create a new instance. But when org.objenesis.strategy.StdInstantiatorStrategy is used, then new instances are created without invoking a no-arg constructor, even if such a constructor is available. This improves Kryo's performance on fast-serialization tests (see issue #138)
* ([3ab6f19](https://github.com/EsotericSoftware/kryo/commit/3ab6f19e58647c33e4be8832af4ea30a771813a6)) Refs #117: Don't export org.objenesis* package (as proposed with patch).
* ([1fc2dc8](https://github.com/EsotericSoftware/kryo/commit/1fc2dc8ad484ab0dc0af6ce86a5bef44c699631e)) Fix #153 Update objenesis to latest version (2.1)
* ([a59cef6](https://github.com/EsotericSoftware/kryo/commit/a59cef66c3f302e42e44f49f18ff28da01dc3dbc)) Fix #140 Add optional OSGI imports for sun.misc and sun.nio.ch
* ([f212086](https://github.com/EsotericSoftware/kryo/commit/f21208643e883fde952ad883fd81e5d7709e87eb)) Fix #156 Depend on minlog and objenesis as standard dependencies
* ([fa2f729](https://github.com/EsotericSoftware/kryo/commit/fa2f729da3c87bfa94f6816ff80e390e0688c5c2)) Fix #158: Remember which fields were removed and when rebuilding the set of fields by means of rebuildCachedFields, remove all fields that were removed before.
* ([a137238](https://github.com/EsotericSoftware/kryo/commit/a1372389ef88218bea2ffda7f8282095b85738d8)) Some progress on #149: Make ObjectField versions for primitive types work in the same way as AsmCacheField and UnsafeCacheField. All of them optimize for speed and ignore any custom registered serializers for primitive types for now.
* ([adf0576](https://github.com/EsotericSoftware/kryo/commit/adf057611a2845c5f6410a9b1b050ef966a5bff5)) Close #155 by fixing a copy&paste error.
* ([8ba1021](https://github.com/EsotericSoftware/kryo/commit/8ba10218f28e452bff1b3f2929e68e08304aa1cf)) Improve Javadocs for UnsafeUtil. And fix the name of the Unsafe class. It is called sun.misc.Unsafe and not java.misc.Unsafe ;-)
* ([bb40b1f](https://github.com/EsotericSoftware/kryo/commit/bb40b1f956ec41ab0ea6502d044d2d9e170c8af7)) Fix java.misc.Unsafe probing. Do not re-throw any exceptions.
* ([0a1c7e3](https://github.com/EsotericSoftware/kryo/commit/0a1c7e326c8b5ffae06ac4f6e03a7fec4aea6753)) Made references optional for copying.
* ([aacf104](https://github.com/EsotericSoftware/kryo/commit/aacf104f7f74d59ebae6535a996c92b58f12d10b)) Better logging of Unsafe-related settings. Ignore any attempts to disable ASM, if Unsafe is not available.
* ([0234f8c](https://github.com/EsotericSoftware/kryo/commit/0234f8c01cf7c409808f9c93aebf7f1235f971d9)) Close #154. Kryo now prefers to use KryoSerializableSerializer if a class implements KryoSerializable
* ([3a110df](https://github.com/EsotericSoftware/kryo/commit/3a110dff7877d0ba9a33df679483bebee3b22dc7)) Avoid implicit references to Unsafe inside FieldSerializer. This should hopefully make it work again on Android.
* ([dbea733](https://github.com/EsotericSoftware/kryo/commit/dbea7337f0631d7a608f401c6df17b43c62b7979)) Void commit to test github jenkins hook
* ([cd79d91](https://github.com/EsotericSoftware/kryo/commit/cd79d9142e46b7f498c1c46615d1a83348be2db0)) Fix issues #148 and #83. Now you can control copying of transient fields by means of FieldSerializer.setCopyTransient. The default is set to copy transient field.
* ([0a8d593](https://github.com/EsotericSoftware/kryo/commit/0a8d593937a282c584156bb67f88c6658852d444)) Use https url for build status link
* ([4a9826a](https://github.com/EsotericSoftware/kryo/commit/4a9826a007964dfd1d18be472cfc023baeaf6ece)) Use new job name for build status link
* ([052ebf2](https://github.com/EsotericSoftware/kryo/commit/052ebf2fa5dc6dc4a90ed04a88c1e45eae3f6846)) Fix build status icon link
* ([5c6da9c](https://github.com/EsotericSoftware/kryo/commit/5c6da9c77286ecf9d42e5403e28d9a6fa07c100c)) Add build status icon
* ([fbf4fcb](https://github.com/EsotericSoftware/kryo/commit/fbf4fcbbbc7a1abe41c9b6fd2cc791b06f3443f4)) Update README.md
* ([4033290](https://github.com/EsotericSoftware/kryo/commit/403329079035832dc2a03a1fe864d4d8d7de80bc)) Update README.md
* ([4f5c274](https://github.com/EsotericSoftware/kryo/commit/4f5c2745e65379c6aba7a25f32fdc2cea574d8fb)) Update README.md
* ([663363a](https://github.com/EsotericSoftware/kryo/commit/663363a0b50bf48e39949840418dcd6bbdb36fc3)) add missing block
* ([7a9eaa2](https://github.com/EsotericSoftware/kryo/commit/7a9eaa2e9ba39bd7b6660fd18c9787947b78ffab)) fix typo
* ([a57c9a9](https://github.com/EsotericSoftware/kryo/commit/a57c9a925db0214a11d0642aabe52ea8ac306076)) Syntax highlighting for README
* ([ac6456a](https://github.com/EsotericSoftware/kryo/commit/ac6456a71eec1c8536872191a524d9a9266d54b3)) Readme
* ([84366e7](https://github.com/EsotericSoftware/kryo/commit/84366e7ac9d575460a94562d7c8755e6104e5937)) Fixed strings of length 1. Added test.
* ([450c503](https://github.com/EsotericSoftware/kryo/commit/450c503cc5e9e915793b98f047281b178f582d3e)) Improve Java serialization, reuse object stream for entire graph.
* ([3addbd9](https://github.com/EsotericSoftware/kryo/commit/3addbd94b6c1c39c6b0ed96c60cb136b9e7fb62d)) Add gitignore
* ([b8c66cf](https://github.com/EsotericSoftware/kryo/commit/b8c66cfc97c6f4504d7e68bc2004fa007dae0a10)) Rename project, kryo2 -> kryo.
* ([7449798](https://github.com/EsotericSoftware/kryo/commit/74497985accf5a28f6c59e91fc24978f7887ef28)) Add link to mailing list
* ([ed080df](https://github.com/EsotericSoftware/kryo/commit/ed080dfa51855aa04d5e9ff5a2993a7084de1472)) Use full url to link to v1 doc
* ([88908c7](https://github.com/EsotericSoftware/kryo/commit/88908c79794f3f8b99b66e91735005ba21bff425)) Try to fix link to v1 doc wiki page
* ([3520f00](https://github.com/EsotericSoftware/kryo/commit/3520f007f5d2c4a956dc9f98a52a2309053d47e0)) Change anchor links to GH markdown
* ([2c3194a](https://github.com/EsotericSoftware/kryo/commit/2c3194a8e64b655ea3de992d4a8a38f8cc315a09)) Add a README.md file for github. This markdown file was automatically generated from the Google Wiki markup of Kryo's Homepage
* ([7d75a49](https://github.com/EsotericSoftware/kryo/commit/7d75a49b089cb1f6e9e8910c9f1a0f1d5fe4430e)) Bad import!
* ([0dbbc2f](https://github.com/EsotericSoftware/kryo/commit/0dbbc2f5b07a9ed737f9e2a562c3697dcefe33a6)) BetterIntMap toString. Fixes #145
* ([859de2e](https://github.com/EsotericSoftware/kryo/commit/859de2ea94aa1e1e8a54c0b763f3e9f5315f0438)) The total() method should return long instead of int (fixes issue #142)
* ([a0da819](https://github.com/EsotericSoftware/kryo/commit/a0da8197565fe42557484897c5a7e2e799b5d7b3)) Fix a bug in IntMap.clear() (issue #144)
* ([a64ddef](https://github.com/EsotericSoftware/kryo/commit/a64ddef69224d1dc4489604f084748d57d6241e3)) Some re-factoring to avoid using Unsafe on platforms which do not support it (e.g. Android). If Unsafe cannot be loaded, Kryo should fallback to ASM-based and reflection-based approaches.
* ([82b9460](https://github.com/EsotericSoftware/kryo/commit/82b9460741aadfd2e294e8b4245791f960527afd)) Take references flag into account when serializing arrays of Strings.
* ([0b9d117](https://github.com/EsotericSoftware/kryo/commit/0b9d11775317f20c72aeb3d5cb333be38ff6d1c6)) Add TreeSetSerializer, closes #139 (Kryo gets ClassCastException when deserializing TreeSet with Comparator)
* ([9d71ad1](https://github.com/EsotericSoftware/kryo/commit/9d71ad17209bbf68134a8dc492922be976fc631f)) Remove unused newSerializer(Class<? extends Serializer> serializerClass, Class type) and fix related javadoc
* ([08db0d8](https://github.com/EsotericSoftware/kryo/commit/08db0d81f79588773fc1cdaaa64b1a4ec79920cf)) Properly serialize empty EnumSets. This fixes issue #91