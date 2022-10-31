# Spell-Checking-and-Autocomplete-Programming-Assignment-
Data Structures and Performance University of California San Diego Course from Coursera.

Programming Assignment: Spell Checking and Autocomplete

Part 1: Spell checking and more benchmarking

This week you learned about binary search trees, and how they can be used to store keys to facilitate more efficient insertion and retrieval than a linked list.  In this section you will implement a dictionary of words, and compare the performance of using a LinkedList vs a Binary Search Tree for this implementation.  In doing this implementation and comparison, you will also be adding the ability to highlight misspelled words in the text editor.

1. Implement the DictionaryLL class which implements the Dictionary interface using a LinkedList data structure.  For this assignment, we are ignoring the case of words.  Your dictionary should store all words as lower case words, i.e. they should be converted to lower case before you put them in.  Similarly, your dictionary should convert a word to lower case before it checks to see whether it is in the Dictionary.  You will have the option to enable case sensitivity (e.g. so "Christine" is considered a word, but "christine" or "CHristine" is flagged as misspelled) in the optional extension to this project, described below.

Test your class by running the JUnit test suite we provide.  Note: there is very little to do to implement this class so if you think it's too easy, you're probably doing it right.

2. Implement the DictionaryBST class which implements the Dictionary interface using a TreeSet (balanced Binary Search Tree) data structure.  For this assignment, we are ignoring the case of words.  Your dictionary should store all words as lower case words, i.e. they should be converted to lower case before you put them in.  Similarly, your dictionary should convert a word to lower case before it checks to see whether it is in the Dictionary.  You will have the option to enable case sensitivity (e.g. so "Christine" is considered a word, but "christine" or "CHristine" is flagged as misspelled) in the optional extension to this project, described below.

Test your class by running the JUnit test suite we provide.  Note: there is very little to do to implement this class so if you think it's too easy, you're probably doing it right.

3. Predict the running time to find words in each Dictionary implementation as a function of n, the number of words in the dictionary.  (Technically because you are converting words to lowercase before you check whether they are in the dictionary, the running time also depends on the length of the word, but we will ignore that here by always looking for a word of the same length). 

4. Run the DictionaryBenchmarking class to time your two dictionary implementations.  We have provided the full implementation of this class, but you might find it helpful to play around with the settings by changing the values of the variables at the top of the file to get better results.   Note that you are testing worst case running time here by always looking for a word that is not present in the dictionary.  

5. Copy and paste your output to Google Sheets as you did for EfficientDocument assignment so that you can graph the running times of both data implementations as the size of the dictionary grows.  You will probably find that the data is very noisy, and in particular you might NOT see a trend you expect with the DictionaryBST class.  Try to think about why that might be.  We'll ask you about it on the quiz.

6. Run the text editor application and see the results of your dictionary implementation.  Now, when you run the application and check the box for Spelling Suggestions, you will see misspelled words highlighted.  You won't be able to see spelling suggestions for the word yet.  That will come in the next Week's assignment.

Part 2: Autocomplete

Next you will implement a Trie data structure to enable the autocomplete functionality of your text editor.  That is, when the user types partial words, the editor will give suggested completions to choose from in a drop down menu under the word.  

1. Examine the files AutoComplete.java and Dictionary.java. These are the two interfaces that your AutoCompleteDictionaryTrie class will implement.  You do not need to change these files.  Just read the comments and understand what each method is supposed to do.

2. Implement the methods addWord, size, isWord and predictCompletions in AutoCompleteDictionaryTrie.java, using a trie data structure to store the words in a dictionary. Each method is described in more detail in the comments in the provided code.

As in part 1, your implementation should convert each word to lowercase before inserting it into the trie.  When you look for a word in the trie, you should look for the all lowercase version of the word.  The methods Character.toLowerCase and/or String.toLowerCase will come in handy here.

Your implementation should make use of the TrieNode class we have provided for you.  You should not need to modify this class at all, but if you want to you may add methods to this class, but you should not remove or modify any of these methods.

Hint for predictCompletions: To write the predictCompletions method, use the breadth first search algorithm Leo described this week.  You'll need a queue, which you can produce by creating a LinkedList and always adding nodes to the back (addLast) and removing them from the front (removeFirst).  In fact, this is the default behavior of the add and remove methods in a LinkedList!  There is some starter code and comments in the provided file that will give you more hints about how to complete this part.

We have also provided for you a helper method to print the trie using a pre-order traversal. You may find this method useful in debugging your code.

You can test your methods using the AutoCompleteDictionaryTrie tester class we provide.  You might want to add additional tests to this class.   You can also find the method calls we will use to grade your implementation in the file TrieGrader.java. See more about this file in the "What to upload for Part 2" section below.
