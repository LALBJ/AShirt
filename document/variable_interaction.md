# 前后端变量交互一致性

### Tips:

**Function** : 模块的功能<br>

**Value** : url(variable[type])<br>

Return : 返回值

### 用户模块 :

| Function | Value                                | Return                           |
| :------- | :----------------------------------- | :------------------------------- |
| 注册     | register(account[Account])           | 1成功, 0失败                     |
| 登录     | login(userId[int], password[String]) | 0用户不存在;1登录成功;-1密码错误 |
| 修改信息 | updateAccount(account[Account])      | 1成功, 0失败                     |
| 退出登录 | exitAccount()                        | 1成功                            |

### 素材提供模块 :

| Function                                                   | Value                                                        | Return                                       |
| :--------------------------------------------------------- | :----------------------------------------------------------- | :------------------------------------------- |
| 获得所有列表                                               | getAllCategory(limit[int], offset[int])                      | Map("rows":List< Category>, "total": 总长度) |
| 根据列表的获得所有图案                                     | getAllItemsByCategoryId(categoryId[int],limit[int], offset[int]) | Map("rows":List< Item>, "total": 总长度)     |
| 根据关键字找到列表                                         | getCategoriesByKeyword(categoryKeyword[String],limit[int], offset[int]) | Map("rows":List< Category>, "total": 总长度) |
| 根据关键字找到款式                                         | getStylesByKeyword(stylesKeyword[String],limit[int], offset[int]) | Map("rows":List< Style>, "total": 总长度)    |
| 根据颜色和款式找到对应的衣服                               | getStyleByColorAndName(color[String], name[String])          | Style                                        |
| 根据款式ID找到对应颜色的衣服（可用在查询衣服可改变的颜色） | getSameStylesByCategoryId(categoryId[int],limit[int], offset[int]) | Map("rows":List< Style>, "total": 总长度)    |
| 根据图案ID找到图案                                         | getItemByItemId(itemId[int])                                 | Item                                         |
| 根据列表ID找到列表                                         | getCategoryByCategoryId(categoryId[int])                     | Category                                     |
| 根据款式ID找到款式                                         | getStyleByStyleId(styleId[int])                              | Style                                        |

### 用户设计模块 :

| Function                                                     | Value                                                        | Return                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------ |
| 获取所有设计                                                 | getAllDesign(limit[int], offset[int])                        | Map("rows":List< Design>, "total": 总长度) |
| 获取当前用户的设计                                           | getDesignOfCurrentUser(limit[int], offset[int])              | Map("rows":List< Design>, "total": 总长度) |
| 根据styleId获取设计                                          | getDesignByStyleId(styleId[int], limit[int], offset[int])    | Map("rows":List< Design>, "total": 总长度) |
| 根据productId获取设计                                        | getDesignByProductId(productId[int], limit[int], offset[int]) | Map("rows":List< Design>, "total": 总长度) |
| 储存用户的一次设计[参考链接](https://www.jianshu.com/p/8ec4deb1579c) | insertDesign(imgFile[MultipartFile], material[String], publich[char], size[String], styleId[int], thought[String]) | 1储存成功, 0储存失败,-1文件上传失败        |
| 更新某条设计                                                 | updateDesign(design[Design])                                 | 1成功, 0失败                               |
| 删除某条设计                                                 | deleteDesign(productId[int])                                 | 1成功, 0失败                               |

### 用户交流模块 :

| Function              | Value                                                        | Return                                       |
| --------------------- | ------------------------------------------------------------ | -------------------------------------------- |
| 获取当前用户的评论    | getCommentsOfCurrentUser(limit[int], offset[int])            | Map("rows":List< Comments>, "total": 总长度) |
| 根据productId获取评论 | getCommentsByProductId(productId[int],limit[int], offset[int]) | Map("rows":List< Comments>, "total": 总长度) |
| 当前用户发表评论      | insertComments(comments[Comments])                           | 1成功, 0失败                                 |

