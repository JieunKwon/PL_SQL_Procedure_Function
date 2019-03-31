# PL_SQL Procedure and Function

 

<a href='https://www.oracle.com/database/technologies/appdev/plsql.html' target='_blank'>Link to Oracle</a>

<a href='https://www.tutorialspoint.com/plsql/plsql_procedures.htm' target='_blank'>Link to tutorials Point/ Procedure</a>   

<a href='https://www.tutorialspoint.com/plsql/plsql_functions.htm' target='_blank'>Link to tutorials Point/ Function</a>   



Why create and use procedure or function
-----

Procedure and Funtion are subprograms that consists of a group of PL/SQL statements.

This subprogram unit is stored as a database object.

Once creating produre or function in a database, can call and use several times. 


Similarities between Procedure and Function
-----

-Both can be called from other PL/SQL blocks.

-If the exception raised in the subprogram is not handled in the subprogram exception handling section, 

then it will propagate to the calling block.

-Both can have as many parameters as required.

-Both are treated as database objects in PL/SQL.


Difference between procedure and function
----

- Functions −  

return a single value; mainly used to compute and return a value.

Use RETURN to return the value and it is mandatory.
              
A Function that contains no DML statements can be called in SELECT statement
              
- Procedures −  

do not return a value directly; mainly used to perform an action.

Use OUT parameter to return the value  
              
Cannot call in SELECT statement
 
 
# < Procedure >

Create and Drop
-------

    << create >>
    
    CREATE [OR REPLACE] PROCEDURE procedure_name
    [(
      parameter_name_1 data_type
      [, parameter_name_2 data_type]...
    )]
    {IS | AS}
      pl_sql_block
     
     << drop >>
     
     DROP PROCEDURE procedure_name

Execute
------

     << call 1 >>
     
     BEGIN
        procedure_name(value1, value2);
     END;

     << call 2 >>
     
     CALL procedure_name(value1, value2);
     
     << call 3 >>
     
     EXECUTE procedure_name(value1, value2);
    
Parameters
------

defalut is IN.

• IN

Procedure must be called with a value for the parameter. 

Value cannot be changed, read-only parameter

• OUT

Procedure must be called with a variable for the parameter. 

Changes to the parameter are seen by the user (i.e., call by reference)

• IN OUT

Value can be sent, and changes to the parameter are seen by the user


Methods for Passing Parameters
-----

• Positional notation

    procedure_name(a, b, c, d);

• Named notation

    procedure_name(x => a, y => b, z => c, m => d);

• Mixed notation

    procedure_name(a, b, c, m => d);
    
    
# < Function >

Create 
-------

Function use RETURN keyword to return the value.

Return is mandatory in functions and the datatype is defined at the time of creation.

    CREATE [OR REPLACE] FUNCTION function_name 
    [(parameter_name [IN | OUT | IN OUT] type [, ...])] 
    RETURN return_datatype 
    {IS | AS} 
    BEGIN 
       < function_body > 
    END [function_name];
    
       
    << example >>
    
    CREATE OR REPLACE FUNCTION totalCustomers 
    RETURN number IS 
       total number(2) := 0; 
    BEGIN 
       SELECT count(*) into total 
       FROM customers; 

       RETURN total; 
    END; 
    / 
    
Execute
-----
    
    << calling funtion above >>
    
    DECLARE 
       c number(2); 
    BEGIN 
       c := totalCustomers(); 
       dbms_output.put_line('Total no. of Customers: ' || c); 
    END; 
    /
    
    => Total no. of Customers: 6  
    
    
