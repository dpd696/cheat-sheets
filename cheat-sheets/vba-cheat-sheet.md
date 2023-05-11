# VBA Cheat Sheet
===============
VBA was created by Microsoft and is the the programming language that
lives within Excel and the Microsoft Office suite of products. This has
made it very popular with companies solving analytics challenges and is
a great language to learn if you're interested in becoming a Business
Intelligence Analyst Data Scientist.

Contents
--------

### [Basic Programming Operations](#basic1)

### [Basic Operations on Data](#basic2)

### [Data Types](#data)

### [Logical/Comparison Operators](#logical)

### [If Statements](#if)

### [Loops](#loops)

### [Arrays](#arrays)

### [The With Construct](#the)

### [Working With Ranges](#working1)

### [Working With Worksheets](#working2)

### [Working With Workbooks](#working3)

### [Useful Keyboard Shortcuts](#useful)

Basic Programming Operations {#basic1}
----------------------------

  Operation                                              Code
  ------------------------------------------------------ -----------------------------------------------------
  Declare a variable                                     Dim myVar As String
  Set the value of a variable                            myVar = "some value"
  Set the value of an object variable                    Set myObj = Range("B2:C3")
  Gather user input                                      userInput = InputBox("What's your favorite color?")
  Print a message to the screen                          MsgBox("You shall not pass!")
  Execute a macro from within another macro              Call myMacro
  Use a built-in worksheet function in a macro           Application.WorksheetFunction.CountA("A:A")
  Comment out a line of code - note the apostrophe (')   'VBA will ignore me!

Basic Operations on Data {#basic2}
------------------------

  Operation                               Code
  --------------------------------------- ----------------------------------
  Addition                                imFour = 2 + 2
  Subtraction                             imZero = 2 - 2
  Multiplication                          imAlsoFour  = 2 \* 2
  Division (uses "/" operator)            MsgBox(10 / 3) 'returns 3.333333
  Integer Division (uses "\\" operator)   MsgBox(10 \\ 3) 'returns 3
  Concatenation                           helloWorld = "Hello" & "world"

Data Types {#data}
----------

  Data Type   Description                                              Example
  ----------- -------------------------------------------------------- ---------------------------------
  Integer     Whole number between -32,768 and 32,767                  11
  Long        Whole numbers between -2,147,483,648 and 2,147,483,647   1,234,567
  Single      Decimal number with seven digits of precision            3.141593
  Double      Decimal number with fifteen digits of precision          3.14159265358979
  Date        Date values                                              3/5/2021
  String      Text data                                                "Hello world"
  Boolean     Logical true/false values                                False
  Range       Range object in Excel                                    Set myRange = Range("A1")
  Worksheet   Worksheet object in Excel                                Set mySheet = Sheets("Sheet 1")
  Workbook    Worksheet object in Excel                                Set myWorkbook = Workbooks(1)
  Variant     Unspecified data type                                    myVariant = "Anything goes!"

Logical/Comparison Operators {#logical}
----------------------------

  Operator                   Symbol   Example
  -------------------------- -------- ---------------------------------
  Equals                     =        5 = 5
  Not Equals                 \<\>     5 \<\> 55
  Greater than               \>       2 \> 1
  Greater than or equal to   \>=      2 \>= 2
  Less than                  \<       4 \< 5
  Less than or equal to      \<=      4 \<= 5
  And                        And      (5 = 5) And (5 \<\> 55) = True
                                      (5 = 5) And (5 = 55) = False
                                      (5 \<\> 5) And (5 = 55) = False
  Or                         Or       (5 = 5) Or (5 \<\> 55) = True
                                      (5 = 5) Or (5 = 55) = True
                                      (5 \<\> 5) Or (5 = 55) = False
  Not                        Not      Not (5 = 5) = False
                                      Not (5 = 55) = True

If Statements {#if}
-------------

  -----------------------------------------------------------------------
  Type                    Example Scenario        VBA Code
  ----------------------- ----------------------- -----------------------
  Simple If statement     If the value stored in  If val \> 1000 Then:\
                          the variable "val" is   MsgBox("Large")\
                          greater than 1,000,     End If
                          print the text          
                          "Large".\               
                          Otherwise, do nothing.  

  If-Else statement       If the value stored in  If val \> 1000 Then:
                          the variable "val" is   MsgBox("Large")\
                          greater than 1,000,     Else: MsgBox("Small")\
                          print the text          End If
                          "Large".\               
                          Otherwise, print the    
                          text "Small".           

  If-ElseIf-Else          If the value stored in  If val \> 1000 Then:
  statement               the variable "val" is   MsgBox("Large")\
                          greater than 1,000,     Else If val \>= 200
                          print the text          Then: MsgBox("Medium")\
                          "Large".\               Else: MsgBox("Small")\
                          If the value stored in  End If
                          the variable "val" is   
                          between 200 and 1,000,  
                          print the text          
                          "Medium". \>\           
                          Otherwise, print the    
                          text "Small".           
  -----------------------------------------------------------------------

Loops {#loops}
-----

  -----------------------------------------------------------------------
  Type                    Example Scenario        VBA Code
  ----------------------- ----------------------- -----------------------
  Do Loop                 Print the first 5       Dim counter As Integer\
                          integers to the screen  counter = 1\
                                                  Do\
                                                  If counter \> 5 Then\
                                                  Exit Do\
                                                  End If\
                                                  MsgBox (counter)\
                                                  counter = counter + 1\
                                                  Loop

  Do While Loop           Print the first 5       Dim counter As Integer\
                          integers to the screen  counter = 1 \
                                                  Do While counter \<= 5\
                                                  MsgBox (counter)\
                                                  counter = counter + 1\
                                                  Loop

  Do Until Loop           Print the first 5       Dim counter As Integer\
                          integers to the screen  counter = 1\
                                                  Do Until counter \> 5\
                                                  MsgBox (counter)\
                                                  counter = counter + 1\
                                                  Loop

  For Next Loop           Print the first 5       Dim counter As
                          integers to the screen  Integer \
                                                  For counter = 1 To 5\
                                                  MsgBox (counter)\
                                                  Next counter

  For Each Loop           Print the values in     Dim cell As Range\
                          cells A1 through A5 to  For Each cell In
                          the screen              Range(\"A1:A5\") \
                                                  MsgBox (cell.Value)\
                                                  Next cell
  -----------------------------------------------------------------------

Arrays {#arrays}
------

  ------------------------------------------------------------------------------------
  Example Scenario                    VBA Code
  ----------------------------------- ------------------------------------------------
  Create an empty array with 5        Dim myArr(5) As Integer
  integer elements and a 0-based      
  index                               

  Set the value at the 3rd position   Dim myArr(5) As Integer\
  of an array with a 0-based index    myArr(2) = 3

  Print the 3rd element of an array   Dim myArr(5)\
  with a 0-based index                myArr(2) = 3\
                                      MsgBox(myArr(2))

  Create an empty 2-dimensional array Dim myArr(2, 1) As Variant
  with 3 rows and 2 columns, that can 
  accommodate multiple data types     

  Set the values of a 3x2 array       Dim myArr(2, 1) As Variant\
                                      myArr(0,0) = "one"\
                                      myArr(0,1) = 1\
                                      myArr(1,0) = "two"\
                                      myArr(1,1) = 2\
                                      myArr(2,0) = "three"\
                                      myArr(2,1) = 3

  Print the maximum index (upper      Dim myArr(5) As String\
  bound) of an array                  MsgBox(UBound(myArr))

  Print all the elements of an array  Dim myArr(2) As Variant\
  using a For Next Loop               myArr(0) = \"one\"\
                                      myArr(1) = 2\
                                      myArr(2) = \"three\"\
                                      \
                                      Dim counter As Integer\
                                      For counter = 0 To UBound(myArr)\
                                      MsgBox (myArr(counter))\
                                      Next counter

  Transfer data from cells A1 through Dim myArr() As Variant\
  A5 to an array                      myArr = Range(\"A1:A5\").Value

  Transfer data from a 3-element      Dim myArr(2) As Variant\
  array to an Excel range             myArr(0) = \"one\"\
                                      myArr(1) = 2\
                                      myArr(2) = \"three\"\
                                      Range(\"A1:C1\") = myArr

  Transfer data from a 3-element      Dim myArr(2) As Variant\
  array to a vertical Excel range     myArr(0) = \"one\"\
                                      myArr(1) = 2\
                                      myArr(2) = \"three\"\
                                      \
                                      Range(\"A1:A3\") =
                                      Application.WorksheetFunction.Transpose(myArr)

  Use the SPLIT function to convert a Dim textStr As String\
  text string into an array of words  Dim splitStr() As String\
                                      textStr = \"I am a list of words\"\
                                      splitStr() = SPLIT(textStr)

  Use the JOIN function to combine an Dim myArr(5) As Variant\
  array of values into a single       Dim combinedStr As String\
  string, with those values separated myArr(0) = \"I\"\
  by spaces                           myArr(1) = "am"\
                                      myArr(2) = \"a\"\
                                      myArr(3) = \"list\"\
                                      myArr(4) = \"of\"\
                                      myArr(5) = \"words\"\
                                      combinedStr = JOIN(myArr, " ")
  ------------------------------------------------------------------------------------

The With Construct {#the}
------------------

  ---------------------------------------------------------------------------
  Example Scenario        VBA Code (without using     VBA Code (using With)
                          With)                       
  ----------------------- --------------------------- -----------------------
  Format cell A1 as       Range(\"A1\").Font.Bold =   With Range(\"A1\").Font
  follows: Bold, Italic,  True\                       .Bold = True\
  Font-style: Roboto,     Range(\"A1\").Font.Italic = .Italic = True\
  Font-size: 14           True\                       .Name = \"Roboto\"\
                          Range(\"A1\").Font.Name =   .Size = 14\
                          \"Roboto\"\                 End With
                          Range(\"A1\").Font.Size =   
                          14                          

  ---------------------------------------------------------------------------

Working With Ranges {#working1}
-------------------

  -----------------------------------------------------------------------
  Example Scenario                    VBA Code
  ----------------------------------- -----------------------------------
  Target a single cell using a        Range("A1")
  hard-coded reference                

  Target multiple cells using a       Range("A1:C3")
  hard-coded reference                

  Print the value of a cell using a   MsgBox(Range("A1").Value)
  hard-coded reference                

  Set the value of a cell using a     Range("A1").Value = 11
  hard-coded reference                

  Print the value of the active cell  MsgBox(ActiveCell.Value)

  Set the value of the active cell    ActiveCell.Value = 22

  Print the value of the cell 1 row   MsgBox(ActiveCell.Offset(1,2))
  below, and 2 columns to the right,  
  of the active cell                  

  Set the value of the cell 1 row     ActiveCell.Offset(-1,-2).Value =
  above, and 2 columns to the left,   "I'm upset that I've been offset!"
  of the active cell                  

  Use the Cells property to print the MsgBox(Cells(1,1))
  value of cell A1                    

  Use the Cells property to set the   Cells(3,4).Value = "Row 3, column
  value of cell D3                    4"

  Use the Cells property within a For Dim counter As Integer\
  Next loop to print the values of    For counter = 1 To 5\
  the first 5 cells in column A       MsgBox (Cells(counter, 1))\
                                      Next counter

  Use the Cells property within a     Dim a As Integer\
  nested For Next loop to print the   Dim b As Integer\
  values of all the cells in a        \
  2-dimensional selection (that is,   For a = 1 To Selection.Rows.Count\
  the cells currently selected by the For b = 1 To\
  user)                               Selection.Columns.Count \
                                      MsgBox (Selection.Cells(a, b))\
                                      Next b\
                                      Next a

  Select the last cell with data in a Range(\"A1\").End(xlDown).Select
  column of values starting in cell   
  A1                                  

  Select all the values in a column   Range(Range(\"A1\"),
  of data starting in cell A1         Range(\"A1\").End(xlDown)).Select
  -----------------------------------------------------------------------

Working With Worksheets {#working2}
-----------------------

  -----------------------------------------------------------------------
  Example Scenario                    VBA Code
  ----------------------------------- -----------------------------------
  Activate a sheet by referencing its Sheets("Sheet 1").Activate
  name                                

  Activate a sheet by referencing its Sheets(1).Activate
  index                               

  Print the name of the active        MsgBox(ActiveSheet.Name)
  worksheet                           

  Add a new worksheet                 Sheets.Add

  Add a new worksheet and specify its Sheets.Add.Name = "My New Sheet"
  name                                

  Delete a worksheet                  Sheets("My New Sheet").Delete

  Hide a worksheet                    Sheets(2).visible = False

  Unhide a worksheet                  Sheets(2).visible = True

  Loop through all sheets in a        Dim ws As Worksheet\
  workbook                            For Each ws In
                                      ActiveWorkbook.Worksheets \
                                      MsgBox (ws.Name)\
                                      Next ws
  -----------------------------------------------------------------------

Working With Workbooks {#working3}
----------------------

  -------------------------------------------------------------------------
  Example Scenario                    VBA Code
  ----------------------------------- -------------------------------------
  Activate a workbook by referencing  Workbooks("My Workbook").Activate
  its name                            

  Activate the first workbook that    Workbooks(1).Activate
  was opened, among all open          
  workbooks                           

  Activate the last workbook that was Workbooks(Workbooks.Count).Activate
  opened, among all open workbooks    

  Print the name of the active        MsgBox(ActiveWorkbook.Name)
  workbook                            

  Print the name of this workbook     MsgBox(ThisWorkbook.Name)
  (the one containing the VBA code)   

  Add a new workbook                  Workbooks.Add

  Open a workbook                     Workbooks.Open("C:\\My
                                      Workbook.xlsx")

  Save a workbook                     Workbooks("My Workbook").Save

  Close a workbook and save changes   Workbooks("My Workbook").Close
                                      SaveChanges:=True

  Close a workbook without saving     Workbooks("My Workbook").Close
  changes                             SaveChanges:=False

  Loop through all open workbooks     Dim wb As Workbook\
                                      For Each wb In Application.Workbooks\
                                      MsgBox (wb.Name)\
                                      Next wb
  -------------------------------------------------------------------------

Useful Keyboard Shortcuts {#useful}
-------------------------

  Press this     To do this
  -------------- --------------------------------------------------------------------------
  Alt+F11        Toggle between the VBA editor and the Excel window
  F2             Open the Object browser
  F4             Open the Properties window
  F5             Runs the current procedure (or resumes running it if it has been paused)
  F8             Starts "debug mode", in which one line of code is executed at a time
  Ctrl + Break   Halts the currently running procedure
  Ctrl+J         List the properties and methods for the selected object

[Back To Top](#contents)