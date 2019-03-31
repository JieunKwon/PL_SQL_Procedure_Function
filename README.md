# PL_SQL_Procedure_Function

PLSQL for procedure and funtion

<a href='https://www.oracle.com/database/technologies/appdev/plsql.html' target='_blank'>Link to Oracle</a>

<a href='https://www.tutorialspoint.com/plsql' target='_blank'>Link to tutorials Point</a>   

Why create and use procedure or function
-----

Once creating produre or function in a database, can call and use several times. 


How different between procedure and function
----

Functions −  return a single value; mainly used to compute and return a value.

Procedures −  do not return a value directly; mainly used to perform an action.


Procedure
---

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
