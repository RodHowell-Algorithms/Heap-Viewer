# Heap Viewer

**Heap Viewer** is an application for creating and manipulating Binary Heaps, Binomial Queues, Leftist Heaps, Randomized Heaps, and Skew Heaps. It uses the package [**edu.ksu.cis.viewer**](https://github.com/RodHowell-Algorithms/Tree-Viewer).

## Installation

To install the application, simply download the JAR archive [`heapviewer.jar`](https://github.com/RodHowell-Algorithms/Heap-Viewer/raw/main/heapviewer.jar). The [Java<sup>TM</sup> SE Runtime Environment (JRE)](https://java.com) is required to run the heap viewer.

## Usage

The program may be started by either opening `heapviewer.jar` or executing the following from a command line in a folder containing this archive:

<pre>
java -jar heapviewer.jar
</pre>

From the main window, select one of the choices from the choice box, and press the Start button. This will open a window in which the heap can be created.

To create and manipulate a heap, enter any integer in the text field in the upper left-hand corner, and press the Put button to add that integer as a priority. Press the RemoveMax button to remove the maximum priority from the heap. The Back and Forward buttons allow you to move through the history of your heap construction. The Clone button opens a new window with an exact copy of the tree and history in your current window; the tree in this window can then be manipulated independently.

## Compiling the Code

If you wish to modify the code, you will need to download a copy, either by cloning it with `git` or by downloading and decompressing a [ZIP archive](https://github.com/RodHowell-Algorithms/Heap-Viewer/archive/refs/heads/main.zip). To compile the code, assuming you have the [Java Development Kit (JDK)](https://www.java.com/en/download/manual.jsp) installed, enter the following from a command line within the root folder of the project (i.e., the one containing the subfolder `edu`):

<pre>
javac -classpath one-jar/lib/viewer.jar edu/ksu/cis/heapviewer/*.java
</pre>

(Depending on your shell, you may need to replace each `/` with `\`.) To run the program after compiling it:

<pre>
java -cp .;one-jar/lib/viewer.jar edu.ksu.cis.heapviewer.Viewer
</pre>

(Depending on your shell, you may need to escape the `;` or replace it with `:`, and/or you may need to replace each `/` with `\`.)

## Creating the JAR Archive

To create a JAR archive, you will first need to create an archive containing just the package **edu.ksu.cis.heapviewer**. Because the command is rather long, the files `options.txt` and `Manifest.txt` have been provided to shorten it:

<pre>
jar -c -f heapviewer-only.jar @options.txt edu/ksu/cis/heapviewer/*.class
</pre>

This creates the Jar archive `heapviewer-only.jar`. It can be run by opening it, but only if the file `viewer.jar` (found in the folder `one-jar/lib`) is in the same folder. These can be packaged together using [One-Jar<sup>TM</sup>](http://one-jar.sourceforge.net/index.php?page=getting-started&file=quickstart). First, move `heapviewer-only.jar` to the folder `one-jar/main`. Then from the `one-jar` folder:

<pre>
jar -c -f ../heapviewer.jar -m boot-manifest.mf .
</pre>

This will create the standalone JAR archive `heapviewer.jar`.