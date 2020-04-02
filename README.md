## SQL
A linguaxe SQL é unha linguaxe da que derivan 6 sublinguaxes:
  
 #### DDL
 (DATA DEFINITION LANGUAGE): CREATE,ALTER,DROP. Opera sobre datos.
 #### DML
 (DATA MANIPULATION LANGUAGE): INSERT,UPDATE,DELETE. Opera sobre datos.
 #### DQL
 (DATA QUERY LANGUAGE): SELECT . Opera sobre os obxectos da Base de Datos.
 Antes do DQL o SELECT estaba metido no DML. 
 #### TCL
 (TRANSACTION CONTROL LANGUAGE): COMMIT, ROLLBACK
 #### DCL
 (DATA CONTROL LANGUAGE): GRANT,REVOKE
 #### SCL
 (SESSION CONTROL LANGUAGE): ALTER SESSION

 ### DDL (CREATE,ALTER,DROP)

  ####  * CREATE
 Empregase para crear base de datos.
 (CREATE DATABASE my DB | CREATE SCHEMA myOther DB).
 Son dúas formas diferentes de crear bases de datos. Diferéncianse nos permisos á hora de crealos.

 Para cerciorarse de que unha base de datos non está creada, a continuación do CREATE ponse o seguinte.
 [IF NOT EXISTS]<nome-da-BD>
	
Ademais, ao crear a táboa hai que referenciar a maneira coa que se van a tratar os datos. Existen catro maneiras:

#####  * NO ACTION
Considérase unha acción por exemplo BORRAR. 
- NO ACTION (Cando hai tablas relacionadas, e se elimina algo na táboa “pai”, sigue existindo nas táboas “filla”). É a opción por defecto.

#####  * CASCADE
-CASCADE (Utilízase para borrar as referencias “pai”, polo cal bórranse as referencias do “fillo”). Efecto cascada.

#####  * SET NULL
- SET NULL (Utilízase para borrar as referencias “pai”, polo cal as referencias “filla” pon un NULL).

#####  * SET DEFAULT
-SET DEFAULT (‘Inventa un campo’, para asignarllo a algo, polo que cando se borra, borrase todo).

 ####  ALTER
 Emprégase para a modificación dunha relación, taboa, tipo de valor, etc unha vez finalizada unha taboa.
 A estrutura é a seguinte:
 ```sql	
ALTER TABLE <Nome-da-taboa> 
```
A continuación, existen dúas posiblilidades: engadir ou eliminar.
 
 ##### 1. AÑADIR
 Para engadir unha taboa ou parte dela, despois do ALTER TABLE <Nome-da-taboa> escríbese un ADD CONSTRAINT e a continuación 
 o nome do elemento a engadir. Por exemplo unha clave foránea. 

```sql	
ALTER TABLE Departamento
  ADD CONSTRAINT FK_Profesor_Departamento
    FOREIGN KEY (Director)
    REFERENCES Profesor
    ON DELETE SET NULL
    ON UPDATE CASCADE;
```
 
 ##### 2. ELIMINAR
 Para eliminar unha taboa ou parte dela, despois do ALTER TABLE <Nome-da-taboa> escríbese un DROP CONSTRAINT e a continuación 
 o nome do elemento a eliminar.
	
```sql
ALTER TABLE Profesor
    DROP CONSTRAINT FK_Grupo_Profesor;
```
 
 ### DML  (INSERT,UPDATE,DELETE)
 #### INSERT
 
 A estrutura é a seguinte:
```sql
INSERT INTO <nome-da-taboa>
[(< atributo >, < atributo2 >)]
(VALUES (< valor1>,<valor2 >) | SELECT );
 	 
```
Cada atributo leva o value. Por exemplo un atributo sería (1,’cheese’,9.99), (2,’bread’, 1.99)
Cada un dos parentesis conterá un atributo.
A estructura será para os VALUES:
```sql	
 	 (<valor1A>,<valor2A>)
	 (<valor1B>,<valor2B>)
	 (<valor1N>,<valor2N>)
```
	
#### SELECT
Mesmo número de columnas e mismos dominios (os dominios sería como un tipo de datos)

#### UPDATE
```sql	
 	 UPDATE < nome-da-táboa >
    	    SET <atributo1> = <valor1>,
        	<atributo2> = <valor2>,
	[WHERE <predicado> ];
```
#### DELETE
```sql	
 	 DELETE FROM  < nome-da-táboa >
	 [WHERE <predicado>];
```

	
	
