# 5.3-Baseball-Stats
[Java Scanner Class](https://www.w3schools.com/java/java_user_input.asp)
[Java Scanner Class Methods](https://www.w3schools.com/java/java_ref_scanner.asp)

The local kids league coach keeps baseball team statistics in a text file organized as follows: each line contains a player's name followed by a list of symbols indicating what happened during each at-bat. The symbols are:
- `h`: hit
- `o`: out
- `w`: walk
- `s`: sacrifice fly

Each item is separated by a comma, and there are no blank spaces except within player names. For example, a file might look like this:

```
Sam Slugger,h,h,o,s,w,w,h,w,o,o,o,h,s
Jill Jenks,o,o,s,h,h,o,o
Will Jones,o,o,w,h,o,o,o,o,w,o,o
```

You are provided with the **BaseballStats.java** skeleton program, which reads and processes a file in this format. Your task is to complete the program, process the stats, and calculate some summary statistics.

---

### Instructions

#### Step 1: Understanding the Starter Code
The starter code provides the basic setup with three `Scanner` objects:
- One `Scanner` (named `scan`) reads the file name from standard input.
- The file name is used to create another `Scanner` (`fileScan`) to operate on the file.
- A third `Scanner` (`lineScan`) is used to parse each line in the file.

#### Step 2: Completing the Program
You will modify the program as follows:

1. **Print each player’s name and at-bat results.**  
   Add a loop that reads each line from the file, parses the player name and at-bat results, and prints them. This will work similarly to the **URLDissector** program in the textbook (Listing 5.11).  
   
   Inside the loop:
   - Read the next line from the file (fileScan.hasNextLine(), fileScan.nextLine()).
   - Create a comma-delimited `Scanner` (lineScan) to parse the line (lineScan = new Scanner(line), lineScan.useDelimiter(",")).
   - Read and print the player’s name.
   - Use a loop to print each at-bat result (`h`, `o`, `w`, `s`) on a new line.

   Example output:
   ```
   Sam Slugger:
   h
   h
   o
   s
   w
   ...
   ```

2. **Modify the loop to count at-bat results.**  
   After ensuring the above code works, modify the inner loop to count the number of:
   - Hits (`h`)
   - Outs (`o`)
   - Walks (`w`)
   - Sacrifices (`s`)

   After counting, compute and print the player’s statistics, including:
   - Hits
   - Outs
   - Walks
   - Sacrifices
   - **Batting Average**: The batting average is the number of hits divided by the total number of hits and outs.

3. **Test the program.**  
   Use the provided **stats.dat** and **stats2.dat** files to test your program.

---

### Starter Code

```java
import java.util.Scanner;
import java.io.*;

public class BaseballStats {
    //-------------------------------------------------
    // Reads baseball stats from a file and counts
    // total hits, outs, walks, and sacrifice flies
    // for each player.
    //-------------------------------------------------
    public static void main(String[] args) throws IOException {
        Scanner fileScan, lineScan;
        String fileName;
        Scanner scan = new Scanner(System.in);
        
        // Read file name
        System.out.print("Enter the name of the input file: ");
        fileName = scan.nextLine();
        fileScan = new Scanner(new File(fileName));
        
        // Read and process each line of the file

    }
}
```

---

### Example Input (stats.dat)

```
Willy Wonk,o,o,h,o,o,o,o,h,w,o,o,o,o,s,h,o,h
Shari Jones,h,o,o,s,s,h,o,o,o,h,o,o,o,o
Barry Bands,h,h,w,o,o,o,w,h,o,o,h,h,o,o,w,w,w,h,o,o
Sally Slugger,o,h,h,o,o,h,h,w
Missy Lots,o,o,s,o,o,w,o,o,o
```

---

### Example Output

```
Willy Wonk:
Hits: 4
Outs: 10
Walks: 1
Sacrifices: 1
Batting Average: 0.286

Shari Jones:
Hits: 3
Outs: 6
Walks: 0
Sacrifices: 2
Batting Average: 0.333

...
```

---

### Grading

1. **Correct File Processing (30 points):**  
   The program should correctly read and process each line from the input file, including names and at-bat results.

2. **Accurate Statistics Calculation (40 points):**  
   The program should correctly count hits, outs, walks, and sacrifices, and calculate the batting average for each player.

3. **Proper Formatting and Output (20 points):**  
   The program should display output in the correct format, showing statistics for each player.

4. **Code Organization and Comments (10 points):**  
   The code should be well-organized with appropriate comments explaining its functionality.



Test your program with both **stats.dat** and **stats2.dat**.