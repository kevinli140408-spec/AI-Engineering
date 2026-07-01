按 `tipo` 列出所有概念页面,带创建日期排序
```dataview
table creado, tags
from "wiki/conceptos"
sort creado desc
```


找出没填 `aliases` 的概念/实体页面
```dataview
list
from "wiki/conceptos" or "wiki/entidades"
where !aliases
```
零出链页面(orphan 辅助检测)
```dataview
list
from "wiki/conceptos" or "wiki/entidades"
where length(file.outlinks) = 0
```
最近7天新增内容
```dataview
table tipo, creado
from "wiki"
where creado >= date(today) - dur(7 days)
sort creado desc
```
