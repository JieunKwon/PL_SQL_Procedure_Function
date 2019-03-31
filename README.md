# PL_SQL_Procedure_Function

PLSQL for procedure and funtion

<a href='https://www.oracle.com/database/technologies/appdev/plsql.html' target='_blank'>Link to Oracle</a>

<a href='https://www.tutorialspoint.com/plsql' target='_blank'>Link to tutorials Point</a>   

Why create and use procedure or function
-----

Once creating produre or function in a database, can call and use several times. 

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
     
     << call >>
     
     BEGIN
        procedure_name(value1, value2);
     END;

     << call >>
     
     CALL procedure_name(value1, value2);
    
Parameters
------

defalut is IN.

• IN

Procedure must be called with a value for the parameter. 

Value cannot be changed

• OUT

Procedure must be called with a variable for the parameter. 

Changes to the parameter are seen by the user (i.e., call by reference)

• IN OUT

Value can be sent, and changes to the parameter are seen by the user


