### 后台删除功能配置 

```js
select * from _sys_fun_field where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_aspect_element  where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_roleobj_funs where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_menu where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_fun_conf_log where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_printset where _sys_fun_id in (select id from _sys_fun where  title like "test%")
select * from _sys_roleobj_funs where _sys_fun_id in (select id from _sys_fun where  title like "test%")
//找到要删除的作业
1._sys_fun
2.根据_sys_fun的ID 删除_sys_aspect_element、_sys_roleobj_funs、_sys_fun_field、_sys_menu、_sys_fun_conf_log、_sys_printset、_sys_roleobj_funs、 _sys_roleobj_funs_rule的外键约束
3.删除作业的表
4.删除_sys_fun
```