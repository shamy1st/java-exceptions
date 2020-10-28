# Java Exceptions
**Exception** is a program error.

### Exception Types
1. **Checked Exception** checked at compile-time, directly inherit Throwable.
   * Example: IOException, SQLException
2. **Unchecked Exception** checked at runtime, inherit RuntimeException.
   * Example: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException
3. **Error**  is irrecoverable (OutOfMemoryError, VirtualMachineError, AssertionError)

### Exception Hierarchy
![](https://github.com/shamy1st/java-exceptions/blob/main/hierarchy.png)

### Catch Exception / Finally Block / Try-With

    public class Main {
        public static void main(String[] args) {
            try (
                var reader = new FileReader("file.txt");
                var writer = new FileReader("output.txt");
            ) {
                var value = reader.read();
            } catch (FileNotFoundException e) {
                e.printStackTrace();
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                //if the external resource class implements AutoClosable interface
                //and you define the external resource in try-with block try()
                //then no need to close the external resource here
                /*
                try {
                    reader.close();
                    writer.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }*/
            }
        }
    }

### 
