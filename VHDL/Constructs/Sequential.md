# Modeling  Sequential Functionality 
## process
- process_name: process(<signaL_name1>, <signaL_name2>, ....)
    --veriable decalarations
    begin
    sequential_signal_assignment_1 
    sequential_signal_assignment_2 
     : 
end process;

- Ex.
    FlipFlop  :  process  (Clock) 
    begin 
        Q <=  D;   
    end  process; 

## Wait  Statements 
- Ex. 
    Proc_Ex1  :  process 
        begin 
            Y1  <=  ’0’; 
            Y2  <=  ’1’; 
            wait; 
    end  process; 
- Ex2.
    Proc_Ex2  :  process 
        begin 
            CLK  <=  ’0’;  wait  for  5  ns; 
            CLK  <=  ’1’;  wait  for  5  ns; 
    end  process; 
- Ex3.
    Proc_Ex3  :  process 
    begin 
        wait  until  (Counter  >  15); -- first  wait  statement 
        RollOver  <=  ’1’;  wait  for  1  ns; -- second  wait  statement 
        RollOver  <=  ’0’; 
    end  process; 
## Sequential Signal Assignment
A <= B

## variable
- variable variable_name : <type> := <initial_value>;

## Conditional Programming Constructs
- Ex.
    if  boolean_condition  then  sequential_statement 
    end  if; 
    if  boolean_condition  then  sequential_statement_1 
    else  sequential_statement_2 
    end  if; 
    if  boolean_condition_1  then  sequential_statement_1 
    elsif  boolean_condition_2  then  sequential_statement_2 
    : 
    : 
    elsif  boolean_condition_n  then  sequential_statement_n 
    end  if; 
    if  boolean_condition_1  then  sequential_statement_1 
    elsif  boolean_condition_2  then  sequential_statement_2 
    : 
    : 
    elsif  boolean_condition_n  then  sequential_statement_n 
    else  sequential_statement_n+1 
    end  if;

| Attribute       | 說明                                                | 回傳型態     |
| --------------- | ------------------------------------------------- | -------- |
| `A’event`       | 當 signal A **值改變** 時為 true，否則 false               | boolean  |
| `A’active`      | 當 signal A **被賦值**（assignment 發生）時為 true，否則 false | boolean  |
| `A’last_event`  | signal A **上一次改變的時間**                             | time     |
| `A’last_active` | signal A **上一次被賦值的時間**                            | time     |
| `A’last_value`  | signal A **上一個值**                                 | 與 A 相同類型 |

| Attribute  | 說明                          | 回傳型態    |
| ---------- | --------------------------- | ------- |
| `B’length` | vector 的長度（例如 8 位元）         | integer |
| `B’left`   | vector 的左邊界（最高位 index，例如 7） | integer |
| `B’right`  | vector 的右邊界（最低位 index，例如 0） | integer |
