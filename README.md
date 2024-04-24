# Fabulous fork

This fork is a copy of the original Gson repository with the following changes:

- `FieldNamingStrategy` interface has a new default method `translateNameWithAlternatives()` that can be overridden so
  that we can create a universal deserializer which supports camelCase and `snake_case` naming conventions when
  deserializing
- `ReflectiveTypeAdapterFactory` uses `fieldNamingPolicy.translateNameWithAlternatives()` to consider alternative json
  field names when deserializing
- updated source version to 1.8
- added dependency to `com.google.j2objc:j2objc-annotations:1.3` and used @Weak and @WeakOuter annotations to avoid
  memory leaks in j2objc

## Building gson and using it in Fabulous Core project

1. Gson is built using maven. Run the following command to build the project:
   ```shell
   mvn source:jar package
   ```
2. this will create a `gson-2.8.8.jar` and `gson-2.8.9-sources.jar` files in the `target` directory
3. copy the above files to `fabulous-core/libs/` directory in the Fabulous Core project

# Gson

Gson is a Java library that can be used to convert Java Objects into their JSON representation. It can also be used to convert a JSON string to an equivalent Java object.
Gson can work with arbitrary Java objects including pre-existing objects that you do not have source-code of.

There are a few open-source projects that can convert Java objects to JSON. However, most of them require that you place Java annotations in your classes; something that you can not do if you do not have access to the source-code. Most also do not fully support the use of Java Generics. Gson considers both of these as very important design goals.

### Goals
  * Provide simple `toJson()` and `fromJson()` methods to convert Java objects to JSON and vice-versa
  * Allow pre-existing unmodifiable objects to be converted to and from JSON
  * Extensive support of Java Generics
  * Allow custom representations for objects
  * Support arbitrarily complex objects (with deep inheritance hierarchies and extensive use of generic types)

### Download

Gradle:
```gradle
dependencies {
  implementation 'com.google.code.gson:gson:2.8.8'
}
```

Maven:
```xml
<dependency>
  <groupId>com.google.code.gson</groupId>
  <artifactId>gson</artifactId>
  <version>2.8.8</version>
</dependency>
```

[Gson jar downloads](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson) are available from Maven Central.

![Build Status](https://github.com/google/gson/actions/workflows/build.yml/badge.svg)

### Documentation
  * [API Javadoc](https://www.javadoc.io/doc/com.google.code.gson/gson): Documentation for the current release
  * [User guide](https://github.com/google/gson/blob/master/UserGuide.md): This guide contains examples on how to use Gson in your code.
  * [Change log](https://github.com/google/gson/blob/master/CHANGELOG.md): Changes in the recent versions
  * [Design document](https://github.com/google/gson/blob/master/GsonDesignDocument.md): This document discusses issues we faced while designing Gson. It also includes a comparison of Gson with other Java libraries that can be used for Json conversion

Please use the ['gson' tag on StackOverflow](https://stackoverflow.com/questions/tagged/gson) or the [google-gson Google group](https://groups.google.com/group/google-gson) to discuss Gson or to post questions.

### Related Content Created by Third Parties
  * [Gson Tutorial](https://www.studytrails.com/java/json/java-google-json-introduction/) by `StudyTrails`
  * [Gson Tutorial Series](https://futurestud.io/tutorials/gson-getting-started-with-java-json-serialization-deserialization) by `Future Studio`
  * [Gson API Report](https://abi-laboratory.pro/java/tracker/timeline/gson/)

### License

Gson is released under the [Apache 2.0 license](LICENSE).

```
Copyright 2008 Google Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

### Disclaimer

This is not an officially supported Google product.
