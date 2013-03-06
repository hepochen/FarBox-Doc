# 文件与图片查找&API

**本文档是针对`/folder/<path>`这个url以及`API`的，并且是通过GET的方式。**

## 使用说明

查询都是通过url进行的，第一步是指定`<path>`; 我们还是看具体示例吧。

### 页面

- `http://image.farbox.com/?type=folder`

- `http://image.farbox.com/?type=image`

- `http://image.farbox.com/folder/folder11/` --> `folder11`实际上是一个文件夹


### API

- `http://image.farbox.com/index`

- `http://image.farbox.com/index?type=image`

- `http://image.farbox.com/folder11/`

- - - - - - - - - - 

## 参数说明

| 参数 | 可能值 | 默认值 | 说明 | 
| --- | ----- | ----- |
| level | `child` `all` | - | `child`仅返回直属的子文档；而`all` 包含子文档的子文档的递归 |
| type | `image` `folder` `file` `post` | - | `file`是指不分类型，`post`类型仅针对API有效 |
| sort | `desc` `asc` | `desc` | 按文件日期排序，desc为最近日期排最先，asc为最近日期排最后|
| page | 整数值 | 1 | 页码，在`/folder/<path>`中无效，仅在API中有效|

**注：默认值为`-`的表明是从模板设置中获取的，具体见[《模板配置项》](/docs/template/configs.md)**

- - - - - - - - - - 

## 全站API (JSON)

**要使用全站API，要确保`configs.index_allowed`是开启的！**

- 查看根目录 `/index`

- 非根目录 `/<folder-path>/`

