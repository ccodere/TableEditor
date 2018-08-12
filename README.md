# TableEditor - A PHP Table viewer and editor

This is a modified version of Robert Hates PHP Table editor and viewer. Since the code is no longer available at the phpguru web site. I am adding the modified code here.

I have also extracted from the Internet archive the guide on how to use it.

Some changes compared to the original version:

To make it work:
* Requires that each table has a primary key.
* The source code should be located in TableEditor/ on your web server
* The css file stylesheet should be located and have the name TableEditor/style.css

CHANGED:
 * No more usage of PHP short tags which is no longer recommended anyways by PHP
 * setConfig now supports the charset attribute which  should be one of the standard character sets that can be used in the <META HTTP-EQUIV="CONTENT-TYPE" CONTENT="text/html; charset...> in the head. This MUST be set before doing anything else.
 * InputType URI permits to create an href link in the table in View mode (not in the main table).
 * Display filters are now applied on the view section
 * When Adding/Editing entries: Empty values in the fields are now set to be equal to NULL when updating them in the table.
 * addValidationCallback() bugfix, the value was not passed by reference in TableEditor.php
 * noViewDisplay() function added which permits to identify  which fields shall be displayed in the View record page,
   compare with noDisplay() which no works for the table view only.
 * dbGetXXX() routines would not escape results, so this would cause problems with escape characters when viewing/editing the data.
 *  Add/Edit: maxLength attribute now used to limit size of input data for following field types: date, time, datetime, text/uri for these values maxLength taken directly from the database, or defaults  to 127 (DEFAULT_MAX_TEXT_LENGTH) characters if it is not valid.
* Add/Edit: Input type visible length is now defined by the lowest  of both values, either DEFAULT_COLUMNS or the maxLength attribute. This is only applicable to these field types: date, time, datetime, text/uri
     

TO DO:
* setInputType('boolean');
* setInputType('uri');
* Bugfix with ambigious columns names in JOINS
* setEditDefaultValue() or something similar to fill up some fields automatically with values when editing them (contrary to creating a new record which uses setDefaultValues()). This is mainly used to create automatically field fields, such a last modification dates of records.
* probably other sutff as it comes up.... such as showing additional non-db information in the view record section.


