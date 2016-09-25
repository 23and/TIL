​#MySql change table column name
````sql
ALTER [ONLINE | OFFLINE] [IGNORE] TABLE tbl_name CHANGE [COLUMN] old_col_name new_col_name column_definition [FIRST|AFTER col_name]
````
````sql
alter table r_table change column old_column new_column bigint(20) unsigned NOT NULL;
````