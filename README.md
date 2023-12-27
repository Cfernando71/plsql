# plsql
plsql EXERCISE

A direção da empresa deseja aumentar o salário de seus funcionários, mas antes disso precisa fazer projeções para avaliar o impacto financeiro. O reajuste deve seguir essas regras : Salário até $ 5.000 aumento de 15%, salário acima de $5.000 e menor que $10.000 aumento de 10% e salário acima de $ 10.000 aumento de 5%. Utilizando PL/SQL escreva um programa no SGBD do Oracle que acesse os dados da tabela de funcionários e informe o valor a mais a ser gasto pela empresa com o aumento de salário.


The company's management wishes to increase the salary of its employees, but before doing so, they need to make projections to assess the financial impact. The salary adjustment should follow these rules: Salary up to $5,000 - 15% increase, salary above $5,000 and less than $10,000 - 10% increase, and salary above $10,000 - 5% increase. Using PL/SQL, write a program in the Oracle database management system that accesses the employee table data and informs the additional amount to be spent by the company with the salary increase.

--CREATE TABLE--

CREATE TABLE FUNCIONARIO (
    ID_FUNCIONARIO INTEGER PRIMARY KEY,
    NOME VARCHAR2(50),
    SALARIO FLOAT 
);

--Inserção de dados Aleatório -- 

DECLARE
    v_id NUMBER;
    v_nome VARCHAR2(50);
    v_salario FLOAT;
BEGIN
    FOR i IN 1..50 LOOP
        v_id := i;
        v_nome := 'Nome' || TO_CHAR(i);
        v_salario := DBMS_RANDOM.VALUE(40000, 80000);

        INSERT INTO FUNCIONARIO (ID_FUNCIONARIO, NOME, SALARIO)
        VALUES (v_id, v_nome, v_salario);
    END LOOP;
END;
/
