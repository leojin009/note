
### mysql8客户端转储mysql5.7数据库

步骤:数据库-工具-转储数据库-选表-下一步-额外的参数命令-增加如下内容

```
--column-statistics=0 --ssl-mode=DISABLED
```


