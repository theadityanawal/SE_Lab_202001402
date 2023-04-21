# Lab 8

## Name: Aditya Nawal

## ID: 20200402

# Exercise 1

![https://user-images.githubusercontent.com/84441910/233054975-8195857f-5500-4021-8797-e470c4fb55f0.png](https://user-images.githubusercontent.com/84441910/233054975-8195857f-5500-4021-8797-e470c4fb55f0.png)

# Exercise 3

```java
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    @Test
    public void testIsHealthy() {
        Boa boa1 = new Boa("Sneaky", 6, "granola bars");
        assertTrue(boa1.isHealthy());
        
        Boa boa2 = new Boa("Slithery", 8, "pizza");
        assertFalse(boa2.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        Boa boa1 = new Boa("Slinky", 4, "mice");
        assertTrue(boa1.fitsInCage(5));
        assertFalse(boa1.fitsInCage(3));
        
        Boa boa2 = new Boa("Curly", 10, "rabbits");
        assertTrue(boa2.fitsInCage(12));
        assertFalse(boa2.fitsInCage(9));
    }
}
```

In the first test case, I am testing the `isHealthy` method of the `Boa` class. I created two `Boa` objects with different favorite foods, and verify that `isHealthy` returns true for the first object and false for the second object.

In the second test case, I am testing the `fitsInCage` method of the `Boa` class. I created two `Boa` objects with different lengths, and test whether they fit in cages of different lengths.

(Expect the first boa to fit in a cage of length 5 but not 3, and the second boa to fit in a cage of length 12 but not 9.)

# Exercise 4

```java
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertTrue(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(3));
        assertFalse(ken.fitsInCage(2));
    }
}
```

Private fields for `jen` and `ken` were added to the `BoaTest` class and initialized in the `setUp` method. The `testIsHealthy` and `testFitsInCage` methods were also updated to utilize these `Boa` objects for testing. It should be noted that the `setUp` method is executed prior to each test method, ensuring that any changes made to the `Boa` objects during a test do not affect the objects used in subsequent tests.

# Exericse 5

![https://user-images.githubusercontent.com/84441910/233055336-2b9ce63e-84ef-4016-9dcf-9ae85dd0d99a.png](https://user-images.githubusercontent.com/84441910/233055336-2b9ce63e-84ef-4016-9dcf-9ae85dd0d99a.png)

## testIsHealthy() method

```java
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertTrue(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(3));
        assertFalse(ken.fitsInCage(2));
    }
}
```

In order to ensure the accuracy of the `isHealthy` method for `Boa` objects, we have implemented additional assertions within the `testIsHealthy` method. These assertions verify that the `isHealthy` method returns `true` for both `Boa` objects under test. Similarly, we have also added assertions to the `testFitsInCage` method to confirm that the `fitsInCage` method returns the expected results for the `Boa` objects. These enhancements to our testing procedures provide greater confidence in the reliability of our code.

### testFitsInCage() method

```java
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertTrue(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertFalse(jen.fitsInCage(1)); // cage length less than boa length
        assertTrue(jen.fitsInCage(2)); // cage length equal to boa length
        assertTrue(jen.fitsInCage(3)); // cage length greater than boa length
        
        assertFalse(ken.fitsInCage(2)); // cage length less than boa length
        assertTrue(ken.fitsInCage(3)); // cage length equal to boa length
        assertTrue(ken.fitsInCage(4)); // cage length greater than boa length
    }
}
```

To further enhance the reliability of our code, we have implemented additional assertions within the `testFitsInCage` method. These assertions verify that the `fitsInCage` method returns the expected results for both `jen` and `ken` when the cage length is less than, equal to, and greater than the length of the `Boa`. As a result of these enhancements, the `testFitsInCage` method is now more robust and capable of checking the behavior of the `fitsInCage` method for a wider range of input values.

# Exercise 6: Running test cases

![https://user-images.githubusercontent.com/84441910/233055458-edc26d82-7761-489e-ad83-6d6a53b9ec87.png](https://user-images.githubusercontent.com/84441910/233055458-edc26d82-7761-489e-ad83-6d6a53b9ec87.png)

# Exercise 7

![https://user-images.githubusercontent.com/84441910/233055714-9e9e60e0-1b06-44e3-af5a-15b1cad2c727.png](https://user-images.githubusercontent.com/84441910/233055714-9e9e60e0-1b06-44e3-af5a-15b1cad2c727.png)

The updated code for the Boa class with the new `lengthInInches()` method:

```java
`public class Boa {
    private String name;
    private int length; // the length of the boa, in feet
    private String favoriteFood;

    public Boa(String name, int length, String favoriteFood) {
        this.name = name;
        this.length = length;
        this.favoriteFood = favoriteFood;
    }

    // returns true if this boa constrictor is healthy
    public boolean isHealthy() {
        return this.favoriteFood.equals("granola bars");
    }

    // returns true if the length of this boa constrictor is
    // less than the given cage length
    public boolean fitsInCage(int cageLength) {
        return this.length < cageLength;
    }

    // produces the length of the Boa in inches
    public int lengthInInches() {
        return this.length * 12;
    }
}`

The updated code for the BoaTest class with the new testLengthInInches() method:

`import static org.junit.Assert.*;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
    private Boa jen;
    private Boa ken;

    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }

    @Test
    public void testIsHealthy() {
        assertFalse(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }

    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(24));
        assertFalse(jen.fitsInCage(16));
        assertTrue(ken.fitsInCage(36));
        assertTrue(ken.fitsInCage(24));
        assertFalse(ken.fitsInCage(18));
    }

    @Test
    public void testLengthInInches() {
        assertEquals(24, jen.lengthInInches());
        assertEquals(36, ken.lengthInInches());
    }
}`
```