A few notes about File I/O
The new Course and Exam Description for 2025-> with College Board / AP Java impacts some of the projects I have previously assigned.

10 Units to 4 Units put a heavy focus on Classes and Objects
Inheritance and Absracts are nearly wiped completely - but will be taught
Recursion is out - but you will be taught and asked about it (continues from CS50)
File Class and File I/O is going to be on the exam - review the CED for your study plans

In that capacity - I have in previous years provided the following code snipped from w3schools 
specifically, from:  "https://www.w3schools.com/java/java_files_read.asp"
- KNOW that this MUST include try/catch structure (and which imports are needed)
- Data is read line by line into a String
- That string will need to be split using the String.split() method with quotes (no regex)
- You CANNOT cast a String to an int 
- - instead use the Integer wrapper class Integer, and the method parseInt() - 


```
import java.io.File;                  // Import the File class
import java.io.FileNotFoundException; // Import this class to handle errors
import java.util.Scanner;             // Import the Scanner class to read text files

public class ReadFile {
  public static void main(String[] args) {
    File myObj = new File("filename.txt");

    // try-with-resources: Scanner will be closed automatically
    try (Scanner myReader = new Scanner(myObj)) {
      while (myReader.hasNextLine()) {
        String data = myReader.nextLine();
        System.out.println(data);
      }
    } catch (FileNotFoundException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```
