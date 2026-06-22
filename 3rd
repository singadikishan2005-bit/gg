
gradle init --type java-application
nano build.gradle

apply plugin: 'java'
apply plugin: 'application'
repositories {
        jcenter()
        mavenCentral()
dependencies {
        compile 'com.google.guava:guava:23.0'
        testCompile 'junit:junit:4.12'
}
        mainClassName = 'com.example.App'
test{
        outputs.upToDateWhen {false}
        testLogging{
                events "passed", "failed", "skipped"
                exceptionFormat "full"
                showStandardStreams=true
        }
}
}

nano  App.java

package com.example;

public class App {
    public static void main(String[] args) {
        double num1 = 5;
        double num2 = 10;

        double sum = num1 + num2;

        System.out.printf("The sum of %.2f and %.2f is %.2f%n", num1, num2, sum);
    }
}

nano AppTest.java

package com.example;

import org.junit.Test;
import static org.junit.Assert.*;

public class AppTest {

    @Test
    public void testAddition() {
        double num1 = 5;
        double num2 = 10;
        double expectedSum = num1 + num2;

        double actualSum = num1 + num2;

        assertEquals(expectedSum, actualSum, 0.01);
    }
}

gradle build
gradle run 
gradle test


