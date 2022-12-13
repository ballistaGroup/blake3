BLAKE3 in Java
---
An unoptimized translation of the blake3 reference implementation from rust to java.
### Maven
```xml
<dependency>
  <groupId>io.github.rctcwyvrn</groupId>
  <artifactId>blake3</artifactId>
  <version>1.3</version>
</dependency>
```
### Examples
```java
        // Hashing bytes
        Blake3 hasher = Blake3.newInstance();
        hasher.update("This is a string".getBytes());
        String hexhash = hasher.hexdigest();
```
```java
        // Hashing files
        Blake3 hasher = Blake3.newInstance();
        hasher.update(new File(filename));
        String filehash = hasher.hexdigest();
```

If what you want are java bindings for the fully optimized blake3, try: https://github.com/sken77/BLAKE3jni


### BALLISTA how to build and install in our own local maven repo

To build, from root folder, run

    mvn clean package

To install into your own local maven repo, from root run

    mvn install:install-file -Dfile=target/blake3-<version | 0.1>.jar -DpomFile=pom.xml