uap-scala
=========

[![Build status](https://travis-ci.org/ua-parser/uap-scala.svg?branch=master)](https://travis-ci.org/ua-parser/uap-scala)
[![Codecov status](https://codecov.io/gh/ua-parser/uap-scala/branch/master/graph/badge.svg)](https://codecov.io/gh/ua-parser/uap-scala)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.uaparser/uap-scala_2.11/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.uaparser/uap-scala_2.11)

A Scala user-agent string parser based on [ua-parser/uap-core](https://github.com/ua-parser/uap-core). It extracts browser, OS and device information.

### Checkout
The code for this repository can be checked out normally. It uses a [git submodule](https://git-scm.com/docs/git-submodule) to include the files needed from [uap-core](https://github.com/ua-parser/uap-core) so care must be taken to make sure the `core` directory is properly checked out and initialized.

Checking out the repo for the first time
```
git clone --recursive https://github.com/ua-parser/uap-scala.git
```
If uap-scala was checked out and core was not properly initialized, the following can be done

```
cd core
git submodule update --init --recursive
```

### Build
To build for the default Scala
```scala
sbt package
```
To cross-build for different Scala versions
```scala
sbt +package
```

### Linking
Linking

You can link against this library in your program at the following coordinates:

Scala 2.10
```
groupId: org.uaparser
artifactId: uap-scala_2.10
version: 0.1.0
```

Scala 2.11
```
groupId: org.uaparser
artifactId: uap-scala_2.11
version: 0.1.0
```

### Usage
```scala
import org.uaparser.scala.Parser

val ua = "Mozilla/5.0 (iPhone; CPU iPhone OS 5_1_1 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9B206 Safari/7534.48.3"
val client = Parser.default.parse(ua) // you can also use CachingParser
println(client) // Client(UserAgent(Mobile Safari,Some(5),Some(1),None),OS(iOS,Some(5),Some(1),Some(1),None),Device(iPhone))
```

### Maintainers

* Piotr Adamski ([@mcveat](https://twitter.com/mcveat)) (Author. Based on the java implementation by Steve Jiang [@sjiang](https://twitter.com/sjiang) and using agent data from BrowserScope)
* [Ahmed Sobhi](https://github.com/humanzz) ([@humanzz](https://twitter.com/humanzz))
