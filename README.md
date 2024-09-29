# ⚠️ 10th of October this library will be moved to https://github.com/wosherco/jnanoid-enhanced, together with the jitpack repo.

# JNanoId Enhanced
[![Jitpack](https://jitpack.io/v/Soundicly/jnanoid-enhanced.svg)](https://jitpack.io/#Soundicly/jnanoid-enhanced)

A unique string ID generator for Java. 

## Why Fork?
Original JNanoId seems to not be maintained anymore. This fork is to add some features.

### Secure
JNanoID uses Java’s [SecureRandom](https://docs.oracle.com/javase/7/docs/api/java/security/SecureRandom.html) to generate cryptographically strong random IDs with a proper distribution of characters.

### Compact
JNanoID generates compact IDs with just 21 characters. By using a larger alphabet than UUID, JNanoID can generate a greater number of unique IDs, when compared to UUID, with fewer characters (21 versus 36).

### URL-Friendly
JNanoID uses URL-friendly characters (`A-Za-z0-9_-`). Perfect for unique identifiers in web applications.

### Customizable
JNanoID is fully customizable. All default options may be overridden. Supply your own Random Number Generator, alphabet, or size.

### Tested
JNanoID is thoroughly tested with JUnit.

## Latest Release

The most recent release is JNanoId 2.0.2.

### Maven

```xml
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>

<dependency>
    <groupId>com.soundicly</groupId>
    <artifactId>jnanoid-enhanced</artifactId>
    <version>main-SNAPSHOT</version>
</dependency>
```

### Gradle

```groovy
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}

dependencies {
    implementation 'com.soundicly:jnanoid-enhanced:main-SNAPSHOT'
}
```

## Usage

JNanoId provides one easy-to-use utility class (`NanoIdUtils`) with two methods to generate IDs.

#### Standard IDs - `randomNanoId()`

The default method creates secure, url-friendly, unique ids. It uses a url-friendly alphabet (`A-Za-z0-9_-`), a secure random number generator, and generates a unique ID with 21 characters.

```java
String id = NanoIdUtils.randomNanoId(); // "ku-qLNv1wDmIS5_EcT3j7"
```

#### Standard IDs with custom length - `randomNanoId(size)`

An additional method that allows you to generate a secure unique ID with a customizable number of characters.

```java
String id = NanoIdUtils.randomNanoId(5); // "f7Yd4"
```

#### Standard IDs with custom alphabet and length - `randomNanoId(alphabet, size)`

An additional method that allows you to generate a secure unique ID with a customizable alphabet and number of characters.

```java

// Use a custom alphabet containing only a, b, and c
char[] alphabet = {'a','b','c'};

String id = NanoIdUtils.randomNanoId(alphabet, 5); // "accab"
```


#### Custom IDs - `NanoIdUtils.randomNanoId(random, alphabet, size);`

An additional method allows you to generate custom IDs by specifying your own random number generator, alphabet, or size.

```java

// Use a faster, but non-secure, random generator
Random random = new Random();

// Use a custom alphabet containing only a, b, and c
char[] alphabet = {'a','b','c'};

// Make IDs 10 characters long
int size = 10;

String id = NanoIdUtils.randomNanoId(random, alphabet, 10); // "babbcaabcb"
```

## Copyright and license

Original Author: [Aventrix LLC](https://www.aventrix.com). 

Code released under the [MIT License](https://github.com/aventrix/jnanoid/blob/master/LICENSE).

Based on the original [NanoId](https://github.com/ai/nanoid) for JavaScript by [Andrey Sitnik](https://github.com/ai/).

## Other Programming Languages

* [C#](https://github.com/codeyu/nanoid-net)
* [Clojure and ClojureScript](https://github.com/zelark/nano-id)
* [Crystal](https://github.com/mamantoha/nanoid.cr)
* [Dart](https://github.com/pd4d10/nanoid)
* [Go](https://github.com/matoous/go-nanoid)
* [Elixir](https://github.com/railsmechanic/nanoid)
* [Haskell](https://github.com/4e6/nanoid-hs)
* [JavaScript](https://github.com/ai/nanoid)
* [Nim](https://github.com/icyphox/nanoid.nim)
* [PHP](https://github.com/hidehalo/nanoid-php)
* [Python](https://github.com/puyuan/py-nanoid)
* [Ruby](https://github.com/radeno/nanoid.rb)
* [Rust](https://github.com/nikolay-govorov/nanoid)
* [Swift](https://github.com/antiflasher/NanoID)

Also, a [CLI tool] is available to generate IDs from the command line.

[CLI tool]: https://github.com/twhitbeck/nanoid-cli
