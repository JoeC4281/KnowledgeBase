Sometimes I want to query my dBASE IV 2.0 .dbf files using Visual FoxPro 9.

I first copy the .dbf file to a temporary folder,
usually my R:\ drive,
which is a RAM Drive.

dBASE IV 2.0 does not have the ability to create or use .CDX index files.

So,
when I USE the .dbf from Visual FoxPro 9,
a dialogue box pops up with the error;

Structural CDX file not found.

One method to avoid this error is to;

SET SAFETY OFF

before USEing the .dbf

Another method is to use the following code;

LOCAL oExc as Exception
TRY
    USE <table>
CATCH TO oExc WHEN oExc.ErrorNo = 1707
    USE <table>
ENDTRY
