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

 ### CREACIÓN DUNHA BASE DE DATOS
 (CREATE DATABASE my DB | CREATE SCHEMA myOther DB)
 Son dúas formas diferentes de crear bases de datos. Diferéncianse nos permisos á hora de crealos.

 Para cerciorarse de que unha base de datos non está creada, a continuación do CREATE ponse o seguinte.
 [ IF NOT EXISTS ]<nome-da-BD>
  [CHARACTER SET <nomedoCharset>]
