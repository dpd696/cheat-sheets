# Excel Cheat Sheet
=================

Contents
--------

### Keyboard Shortcuts

-   [Navigating Worksheets](#navigating-worksheets)
-   [Selecting Cells](#selecting-cells)
-   [Editing Cells](#editing-cells)
-   [Formatting Cells](#formatting-cells)
-   [Editing Data & Formulas](#editing-data-&-formulas)
-   [Working with Worksheets &
    Workbooks](#working-with-worksheets-&-workbooks)
-   [Miscellaneous](#miscellaneous)

### The 10% Of Excel Functions You\'ll Use 99% Of The Time

-   [Date & Time Functions](#date-&-time-functions)
-   [Financial Functions](#financial-functions)
-   [Information Functions](#information-functions)
-   [Logical Functions](#logical-functions)
-   [Lookup Functions](#lookup-functions)
-   [Mathematical Functions](#mathematical-functions)
-   [Statistical Functions](#statistical-functions)
-   [Text Functions](#text-functions)

### Handy Excel Formula & Function \"Recipes\"

-   [Offset date values with the DATE
    function](#offset-date-values-with-the-DATE-function)
-   [Use EOMONTH to return the first day of the
    months](#use-EOMONTH-to-return-the-first-day-of-the-month)
-   [Error-proof lookups with IFERROR and
    VLOOKUP](#error-proof-lookups-with-IFERROR-and-VLOOKUP)
-   [Classify a lookup value as \"found\" or \"not found\" in a list
    with ISERROR and
    MATCH](#classify-a-lookup-value-as-found-or-not-found-in-a-list-with-ISERROR-and-MATCH)
-   [Create a multi-level classification with nested IF
    functions](#create-a-multi-level-classification-with-nested-IF-functions)
-   [Apply complex logical conditions with IF +
    AND](#apply-complex-logical-conditions-with-IF-+-AND)
-   [Combine INDEX and MATCH for two-way
    lookups](#combine-INDEX-and-MATCH-for-two-way-lookups)
-   [Randomly sample data with RANDBETWEEN and
    INDEX](#randomly-sample-data-with-RANDBETWEEN-and-INDEX)
-   [Use TEXT to return the name of the current day of the
    week](#use-TEXT-to-return-the-name-of-the-current-day-of-the-week)
-   [Dynamically extract a person\'s first name with FIND and
    LEFT](#dynamically-extract-a-person's-first-name-with-FIND-and-LEFT)
-   [Remove multiple characters from a text string with nested
    SUBSTITUTE
    functions](#remove-multiple-characters-from-text-string-with-nested-SUBSTITUTE-functions)

### Common Formula Errors

-   [Common Formula Errors](#common-formula-errors)

Keyboard Shortcuts
------------------

### Navigating Worksheets

  Excel for Windows   Excel for Mac        Shortcut Description
  ------------------- -------------------- ---------------------------------------------------------------------------------
  Ctrl+Home           Fn+Ctrl+Left Arrow   Navigates to cell A1 of the given worksheet.
  Ctrl+Right Arrow    Ctrl+Right Arrow     Navigates to the right edge of the current row, in the current data region.
  Ctrl+Left Arrow     Ctrl+Left Arrow      Navigates to the left edge of the current row, in the current data region.
  Ctrl+Up Arrow       Ctrl+Up Arrow        Navigates to the top edge of the current column, in the current data region.
  Ctrl+Down Arrow     Ctrl+Down Arrow      Navigates to the bottom edge of the current column, in the current data region.
  Ctrl+End            Ctrl+End             Navigates to the last cell used in the current worksheet.

### Selecting Cells

  Excel for Windows        Excel for Mac               Shortcut Description
  ------------------------ --------------------------- ------------------------------------------------------------------------------------------------
  Ctrl+Spacebar            Ctrl+Spacebar               Selects an entire worksheet column.
  Shift+Spacebar           Shift+Spacebar              Selects an entire worksheet row.
  Ctrl+Shift+Up Arrow      Ctrl+Shift+Up Arrow         Extends the selection of cells to the last cell at the top edge of the current data region.
  Ctrl+Shift+Down Arrow    Ctrl+Shift+Down Arrow       Extends the selection of cells to the last cell at the bottom edge of the current data region.
  Ctrl+Shift+Right Arrow   Ctrl+Shift+Right Arrow      Extends the selection of cells to the last cell at the right edge of the current data region.
  Ctrl+Shift+Left Arrow    Ctrl+Shift+Left Arrow       Extends the selection of cells to the last cell at the left edge of the current data region.
  Ctrl+Shift+Home          Fn+Ctrl+Right Arrow         Extends the selection of cells up and to the left, to cell A1.
  Ctrl+Shift+End           Fn+Ctrl+Shift+Right Arrow   Extends the selection of cells down and to the right, to the last used cell in the worksheet.
  Ctrl+A                   Command+A                   Selects all the cells in the current data region of the worksheet.

### Editing Cells

  Excel for Windows   Excel for Mac    Shortcut Description
  ------------------- ---------------- ---------------------------------------------------------------------------------------------------------
  Ctrl+C              Command+C        Copies the selected cells or content.
  Ctrl+V              Command+V        Pastes the copied cells or content.
  Ctrl+Alt+V          Command+Ctrl+V   Displays the Paste Special dialog box; available only after something has been copied to the clipboard.
  Ctrl+X              Command+X        Cuts the selected cells or content.
  Ctrl+F              Command+F        Displays the Find and Replace dialog, with the Find tab selected.
  Ctrl+H              Ctrl+H           Displays the Find and Replace dialog, with the Replace tab selected.

### Formatting Cells

  Excel for Windows   Excel for Mac   Shortcut Description
  ------------------- --------------- ------------------------------------------
  Ctrl+1              Ctrl+1          Displays the format cells dialog box.
  Ctrl+B              Command+B       Applies or removes bold formatting.
  Ctrl+U              Command+U       Applies or removes underline formatting.
  Ctrl+I              Command+I       Applies or removes italic formatting.

### Editing Data & Formulas {#editing-data-&-formulas}

  Excel for Windows   Excel for Mac        Shortcut Description
  ------------------- -------------------- --------------------------------------------------------------------------------------------------
  Alt+Enter           Ctrl+Option+Return   Moves the cursor to a new line in the cell being edited.
  Shift+Right Arrow   Shift+Right Arrow    Selects a character to the right of cursor.
  Shift+Left Arrow    Shift+Left Arrow     Selects a character to the left of cursor.
  F2                  Control+U            Edits (places the cursor in) the active cell.
  F9                  Fn+F9                Calculates all worksheets in all open workbooks.
  F4                  F4                   Cycles through combinations of absolute and relative references for the selected cell reference.

### Working With Worksheets & Workbooks {#working-with-worksheets-&-workbooks}

  Excel for Windows   Excel for Mac   Shortcut Description
  ------------------- --------------- -------------------------------------------
  Ctrl+O              Command+O       Displays the menu for opening a workbook.
  Ctrl+N              Command+N       Creates a new workbook.
  Ctrl+W              Command+W       Closes the active workbook window.
  Ctrl+S              Command+S       Saves the current workbook.
  Shift+F11           Fn+Shift+F11    Inserts a new worksheet.

### Miscellaneous

  Excel for Windows   Excel for Mac      Shortcut Description
  ------------------- ------------------ -----------------------------------------------------------------------------------
  Ctrl+Z              Command+Z          Undo last action.
  Ctrl+Y              Command+Y          Redo last action.
  Ctrl+Shift+L        Command+Shift +F   Adds or removes Autofilters from the current data region.
  Ctrl+T              Ctrl+T             Inserts a table based on either the current selection or the current data region.
  Alt+F11             Fn+Option+F11      Displays the VBA Editor.
  F1                  F1                 Displays the Excel Help task pane.
  F7                  F7                 Displays the Spellcheck dialog box.

The 10% of Excel Functions You'll Use 99% of the Time
-----------------------------------------------------

Brackets surrounding an argument in function syntax (e.x.,
\[argument1\]) indicate that the argument is optional.

### Date & Time Functions {#date-&-time-functions}

  Function      Description                                                                                         Syntax
  ------------- --------------------------------------------------------------------------------------------------- -------------------------------------------------------
  DATE          Returns a date based on inputs of year, month, and day.                                             DATE(year,month,day)
  DATEDIF       Calculates the number of days, months, or years between two dates.                                  DATEDIF(start\_date,end\_date,unit)
  DAY           Converts a date value to a day of the month.                                                        DAY(serial\_number)
  EOMONTH       Returns the date value of the last day of the month before or after a specified number of months.   EOMONTH(start\_date, months)
  MONTH         Converts a date value to a month.                                                                   MONTH(serial\_number)
  NETWORKDAYS   Returns the number of whole workdays between two dates.                                             NETWORKDAYS(start\_date, end\_date, \[holidays\])
  NOW           Returns the current date and time.                                                                  NOW() - The NOW function syntax has no arguments.
  TODAY         Returns today\'s date.                                                                              TODAY() - The TODAY function syntax has no arguments.
  WEEKDAY       Converts a date value to a day of the week.                                                         WEEKDAY(serial\_number,\[return\_type\])
  YEAR          Converts a date value to a year.                                                                    YEAR(date\_value)

### Financial Functions

  Function   Description                                                                                                    Syntax
  ---------- -------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------
  FV         Returns the future value of an investment based on periodic, constant payments and a constant interest rate.   FV(rate,num\_periods,payment,\[present\_value\],\[type\])
  PMT        Calculates the payment on a loan based on constant payments and a constant interest rate.                      PMT(rate, num\_periods, present\_value, \[future\_value\], \[type\])

### Information Functions

  Function   Description                                                      Syntax
  ---------- ---------------------------------------------------------------- -----------------
  ISBLANK    Checks whether a value is blank, and returns TRUE or FALSE.      ISBLANK(value)
  ISERROR    Checks whether a value is an error, and returns TRUE or FALSE.   ISERROR(value)
  ISNUMBER   Checks whether a value is a number, and returns TRUE or FALSE.   ISNUMBER(value)

### Logical Functions

  Function   Description                                                                                                     Syntax
  ---------- --------------------------------------------------------------------------------------------------------------- ----------------------------------------------------
  AND        Tests whether all arguments are TRUE, and returns TRUE if so, FALSE if not.                                     AND(logical1,logical2,...)
  IF         Returns one value if a specified logical condition is met, and an alternate value if it is not.                 IF(logical\_test,value\_if\_true,value\_if\_false)
  IFERROR    Returns a value you specify if a formula evaluates to an error; otherwise, returns the result of the formula.   IFERROR(value, value\_if\_error)
  NOT        Changes FALSE to TRUE, and TRUE to FALSE.                                                                       NOT(logical)
  OR         Tests whether any arguments are TRUE, and returns TRUE if so, FALSE if not.                                     OR(logical1,logical2,...)

### Lookup Functions

  Function   Description                                                                                                                                                                                    Syntax
  ---------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------
  HLOOKUP    Searches for a lookup value in the top row of an range; if a match is found, HLOOKUP returns the value of a cell in the same column, but offset a specified number of rows down.               HLOOKUP(lookup\_value, table\_array, row\_index\_num, \[range\_lookup\])
  INDEX      Uses an index to choose a value from a reference or array.                                                                                                                                     INDEX(array, row\_num, \[column\_num\])
  MATCH      Looks up values in a reference or array, and returns their position.                                                                                                                           MATCH(lookup\_value, lookup\_array, \[match\_type\])
  VLOOKUP    Searches for a lookup value in the first column of a range; if a match is found, VLOOKUP returns the value of a cell in the same row, but offset a specified number of columns to the right.   VLOOKUP (lookup\_value, table\_array, col\_index\_num, \[range\_lookup\])

### Mathematical Functions

  Function      Description                                                          Syntax
  ------------- -------------------------------------------------------------------- ----------------------------------------------------------------------------------------
  ABS           Returns the absolute value of a number.                              ABS(number)
  MOD           Returns the remainder after a number is divided by another number.   MOD(number, divisor)
  ROUND         Rounds a number to a specified number of digits.                     ROUND(number, num\_digits)
  ROUNDDOWN     Rounds a number down, toward zero.                                   ROUNDDOWN(number, num\_digits)
  ROUNDUP       Rounds a number up, away from zero.                                  ROUNDUP(number, num\_digits)
  RAND          Returns a random real number between 0 and 1.                        The RAND function syntax has no arguments.
  RANDBETWEEN   Returns a random integer between two integers you specify.           RANDBETWEEN(bottom, top)
  SUM           Adds all the numbers in a range of cells.                            SUM(number1,\[number2\],\...)
  SUMIF         Sums the values in a range that meet criteria that you specify.      SUMIF(range, criteria, \[sum\_range\])
  SUMIFS        Adds all of its arguments that meet multiple criteria.               SUMIFS(sum\_range, criteria\_range1, criteria1, \[criteria\_range2, criteria2\], \...)
  SUMPRODUCT    Returns the sum of the products of corresponding ranges or arrays.   SUMPRODUCT(array1, \[array2\], \[array3\], \...)

### Statistical Functions

  Function     Description                                                                                     Syntax
  ------------ ----------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------
  AVERAGE      Returns the average (arithmetic mean) of the arguments.                                         AVERAGE(number1, \[number2\], \...)
  AVERAGEIF    Returns the average (arithmetic mean) of all the cells in a range that meet a given criteria.   AVERAGEIF(range, criteria, \[average\_range\])
  AVERAGEIFS   Returns the average (arithmetic mean) of all cells that meet multiple criteria.                 AVERAGEIFS(average\_range, criteria\_range1, criteria1, \[criteria\_range2, criteria2\], \...)
  COUNT        Counts how many numbers are in the list of arguments.                                           COUNT(value1, \[value2\], \...)
  COUNTA       Counts how many values (numeric and non-numeric) are in the list of arguments.                  COUNTA(value1, \[value2\], \...)
  COUNTBLANK   Count the number of empty cells in a range of cells.                                            COUNTBLANK(range)
  COUNTIF      Counts the number of cells within a range that meet the given criteria.                         COUNTIF(range, criteria)
  COUNTIFS     Counts the number of cells within a range that meet multiple criteria.                          COUNTIFS(criteria\_range1, criteria1, \[criteria\_range2, criteria2\]...)
  MAX          Returns the maximum value in a list of arguments.                                               MAX(number1, \[number2\], \...)
  MEDIAN       Returns the median of the given numbers.                                                        MEDIAN(number1, \[number2\], \...)
  MIN          Returns the minimum value in a list of arguments.                                               MIN(number1, \[number2\], \...)
  STDEV.P      Calculates standard deviation based on the entire population, given as arguments.               STDEV.P(number1,\[number2\],\...)

### Text Functions

  Function      Description                                                                                                                                        Syntax
  ------------- -------------------------------------------------------------------------------------------------------------------------------------------------- -----------------------------------------------------------
  CONCATENATE   Joins two or more text strings into one string.                                                                                                    CONCATENATE(text1, \[text2\], \...)
  FIND          Returns the starting position of one text string within another text string (case sensitive).                                                      FIND(find\_text, within\_text, \[start\_num\])
  LEFT          Returns the first character or characters in a text string, based on the number of characters you specify.                                         LEFT(text, \[num\_chars\])
  LEN           Returns the number of characters in a text string.                                                                                                 LEN(text)
  LOWER         Converts text to lowercase.                                                                                                                        LOWER(text)
  MID           Returns a specific number of characters from a text string, starting at the position you specify, based on the number of characters you specify.   MID(text, start\_num, num\_chars)
  PROPER        Capitalizes the first letter in each word of a text string.                                                                                        PROPER(text)
  RIGHT         Returns the rightmost characters from a text string.                                                                                               RIGHT(text)
  SUBSTITUTE    Substitutes new text for old text in a text string.                                                                                                SUBSTITUTE(text, old\_text, new\_text, \[instance\_num\])
  TEXT          Changes the way a number appears by applying formatting to it with format codes.                                                                   TEXT(value, text\_format)
  TRIM          Removes all spaces from text except for single spaces between words.                                                                               TRIM(text)
  UPPER         Converts text to uppercase.                                                                                                                        UPPER(text)

Handy Excel Formula & Function "Recipes"
----------------------------------------

### Offset date values with the DATE function {#offset-date-values-with-the-DATE-function}

  Scenario                                                       Syntax
  -------------------------------------------------------------- ----------------------------------------------------
  Dynamically calculate a date 3 months from the current date.   =DATE(YEAR(TODAY()),MONTH(TODAY())+3,DAY(TODAY()))

### Use EOMONTH to return the first day of the month {#use-EOMONTH-to-return-the-first-day-of-the-month}

  Scenario                                                 Syntax
  -------------------------------------------------------- ------------------------
  Dynamically return the first day of the current month.   =EOMONTH(TODAY(),-1)+1

### Error-proof lookups with IFERROR and VLOOKUP {#error-proof-lookups-with-IFERROR-and-VLOOKUP}

  Scenario                                                            Syntax
  ------------------------------------------------------------------- ---------------------------------------------------------------
  Return a customized error message if VLOOKUP can\'t find a value.   =IFERROR(VLOOKUP(A2,Sheet2!A:B,2,FALSE),\"Value not found.\")

### Classify a lookup value as \"found\" or \"not found\" in a list with ISERROR and MATCH {#classify-a-lookup-value-as-found-or-not-found-in-a-list-with-ISERROR-and-MATCH}

  Scenario                                                                                                          Syntax
  ----------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------
  Return \"Found\" if the keyword \"Excel\" is found in a list of names in column A, and \"Not found\" otherwise.   =IF(ISERROR(MATCH(\"Excel\",A:A,0)),\"Not found\",\"Found\")

### Create a multi-level classification with nested IF functions {#create-a-multi-level-classification-with-nested-IF-functions}

  Scenario                                                                                                      Syntax
  ------------------------------------------------------------------------------------------------------------- --------------------------------------------------------
  Classify a product price in cell A1 as \"High\" (\> \$1,000), \"Medium\" (\>= \$200), or \"Low\" (\< \$200)   =IF(A1\>1000,\"High\",IF(A1\>=200,\"Medium\",\"Low\"))

### Apply complex logical conditions with IF + AND {#apply-complex-logical-conditions-with-IF-+-AND}

  Scenario                                                                                                                                                                                                                                         Syntax
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ ---------------------------------------------
  Calculate whether a salesperson qualified for a bonus by testing whether they exceeded their sales goal of \$1,000,000 *and* their new accounts goal of 20. The value for sales is in cell A1, while the value for new accounts is in cell B1.   =IF(AND(A1\>1000000,B1\>20),\"Yes\",\"No\")

### Combine INDEX and MATCH for two-way lookups {#combine-INDEX-and-MATCH-for-two-way-lookups}

  Scenario                                                                                                                                                                            Syntax
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------
  Return a grade from a two-way matrix (column AND row headers) of student names and class names in cells A1:J10, at the intersection of \"Excel\" (rows) and \"Travis\" (columns).   =INDEX(A1:J10,MATCH(\"Excel\",A1:A10,0),MATCH(\"Travis\",A1:J1,0))

### Randomly sample data with RANDBETWEEN and INDEX {#randomly-sample-data-with-RANDBETWEEN-and-INDEX}

  Scenario                                                          Syntax
  ----------------------------------------------------------------- ----------------------------------
  Randomly select a name from a list of 10 names in cells A1:A10.   =INDEX(A1:A10,RANDBETWEEN(1,10))

### Use TEXT to return the name of the current day of the week {#use-TEXT-to-return-the-name-of-the-current-day-of-the-week}

  Scenario                                          Syntax
  ------------------------------------------------- -------------------------
  Return the name of the current day of the week.   =TEXT(TODAY(),\"dddd\")

### Dynamically extract a person\'s first name with FIND and LEFT {#dynamically-extract-a-person's-first-name-with-FIND-and-LEFT}

  Scenario                                                                               Syntax
  -------------------------------------------------------------------------------------- ----------------------------
  Return the first name from a person\'s name stored in cell A1, regardless of length.   =LEFT(A1,FIND(\" \",A1)-1)

### Remove multiple characters from a text string with nested SUBSTITUTE functions {#remove-multiple-characters-from-a-text-string-with-nested-SUBSTITUTE-functions}

  Scenario                                                       Syntax
  -------------------------------------------------------------- ---------------------------------------------------
  Remove all periods and commas from a text string in cell A1.   =SUBSTITUTE(SUBSTITUTE(A1,\".\",\"\"),\",\",\"\")

Common Formula Errors
---------------------

### Common Formula Errors {#common-formula-errors}

  Error          Description
  -------------- ----------------------------------------------------------------------------------------------------------
  \#DIV/0        The formula attempts to divide a number by zero.
  \#NAME?        Some part of the formula references a name (for example, a function name) that Excel doesn\'t recognize.
  \#VALUE!       One or more function arguments have been supplied with data that is incompatible with the argument.
  \#REF!         The formula references a cell that no longer exists.
  \#\#\#\#\#\#   The value is too wide to fit within its column.

[Back To Top](#contents)