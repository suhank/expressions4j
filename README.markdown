# About

Expressions4j a project intended to embed expressions to Java programs. The typical use-cases is
when you need to generate expression from user input or expose some rules to configuration files.

# Getting expressions4j

* Direct jars downloads: [expressions4j-1.2](http://maven.scalemotion.com/open/com/scalemotion/expressions4j/expressions4j/1.2/)
* Plugin a maven repository to pom.xml

        <repository>
            <id>scalemotion-open</id>
            <url>http://maven.scalemotion.com/open/</url>
        </repository>

and use it as dependency

        <dependency>
            <groupId>com.scalemotion.expressions4j</groupId>
            <artifactId>expressions4j</artifactId>
            <version>1.2</version>
        </dependency>

# Usage

## Advantages

* API is language-agnostic. Using some API you could treat expressions as Java or JavaScript (Groovy/Scala support is planned).
Of cause, expressions syntax would be different for different language).
* Excellent API/Interoperability: it allows to expose functions/constants/variables to your expressions very easily
* It's lightweigh. It has zero dependecies. You should plug [javassist](http://www.csg.is.titech.ac.jp/~chiba/javassist/)/[Rhino](http://www.mozilla.org/rhino/) library
to classpath depending on which language you're using.

## Basic examples

    System.out.println(new JavaExpressionCompiler().compile("return 2 + 2;", Object.class, int.class).evaluate(null));
    //will output 4

    System.out.println(new JSExpressionCompiler().compile("5 * 5;", Object.class, int.class).evaluate(null));

## Dependencies

expressions4j has 0 runtime dependencies itself. However you should plugin javassist/rhino/both library depending of what kind of expressions are you going to use.
expressions4j was tested with javassisit 3.12.1.GA and rhino 1.7R2. It also should work with higher major versions. If you're using maven you might plugin one of (or both):
        <dependency>
            <groupId>rhino</groupId>
            <artifactId>js</artifactId>
            <version>1.7R2</version>
        </dependency>
        <dependency>
            <groupId>javassist</groupId>
            <artifactId>javassist</artifactId>
            <version>3.12.1.GA</version>
        </dependency>

## API

The well documented examples is the best doc: https://github.com/ScaleMotion/expressions4j/blob/master/src/main/java/com/scalemotion/expressions4j/examples/Examples.java

