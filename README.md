#How to run code and tests

To run the code:
  1. Install the `luhn-0.2.0` package
     * Have `luhn-0.2.0.tar.gz` package (which is already in the folder)
     * Under the directory of folder, install with command `pip install luhn`
     * More info: https://pypi.python.org/pypi/luhn
  2. Run the code:
     * Under the directory of folder, run with command:
       `python main.py < input.txt`
       `input.txt` is the name of input file. I assume it's a space delimited
       `txt` file when wrote the program.
  3. Check the output:
     * After we run the code, output file `output.txt` will show up under the
       directory of folder.

To run the test:
  1. Make sure `unittest` package is installed
     * It is a Python standard package. So it's installed in most situations.
     * More info: https://docs.python.org/3/library/unittest.html
  2. Run the test:
     * Under the directory of folder, run with command:
       `python cardTest.py`


#Overview of design decisions

1. `main.py` is the executable. It has two parts: process the input
    and write the output summary.

2. `processInfo.py` contains all functions that process information.
    * `processLine` parses the space delimited input information. It
       returns the arguments of an input command line.
    * `getSummary` gets the summary of input card. It returns the space
      delimited summary that matches output format.

3. `Card.py` contains the Card class. Card object stores the information
    of a card, and allows operations of add, check card information,
    charge and credit.

4. Card object has the following data members:
    * `name`: name of the card holder.
    * `number`: number of the card.
    * `limit`: limit of the card.
    * `balance`: balance of the card.

5. Card object has the following methods:
    * Initialize: `name`, `number`, and `limit` could create a new card.
      If the card number is valid, the initial `balance` will be `0`; or
      the initial `balance` will be `"error"`.
    * `charge`: increases the balance of the card by specified amount.
    * `credit`: decreases the balance of the card by specified amount.
    * `cardInfo`: returns the card information.

6. `cardVerify.py` contains the function `cardVerify` that checks if the
    card number is valid using Luhn 10.

#Why pick Python as programming language

* There are a lot of lightweight and useful Python packages. For example,
  the `luhn-0.2.0` included in this program is nice and small. If I am
  going to extend my code, these packages help realize the functionality
  better.
* Python is object-oriented and dynamic, which is suitable for implementing
  the Card class here. Personally, I am more familiar with Python and prefer
  building small applications in Python.

