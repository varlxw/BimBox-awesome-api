> #  BIMBox.Viewing.API.OBVApi.OBVConfig.registerContextMenuCallback
>
> ---

####  注册自定义视图环境菜单的回调函数。

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | string | 回调函数的id |
| callback |   function\(array, object\) |   回调函数。 第一个参数为菜单项的数组，菜单项为{ title, target }，其中 title 是菜单项的名称，target 为点击 此菜单项时的响应函数； 第二个参数为当前视图状态对象，为{ hasSelected, hasVisible, hasHidden }，其中 hasSelected 表示当 前视图中存在已选中的对象，hasVisible 表示选择集 中包含显示的对象，hasHidden 表示选择集中包含隐 藏的对象。 |

```js
obvapi.registerContextMenuCallback('MyMenuItems', function (menu, status) {
    if (status.hasSelected) {
        //删除内置菜单
        //内置菜单名称为："Focus", "Isolate", "Hide Selected", "Show Selected",
        // * "Show All Objects"， "Clear Selection"， "Move Objects"， "Reset Objects"
        for (var index= menu.length -1; index>=0; --index) {
            if(menu[index].title == "Move Objects"|| menu[index].title == "Reset Objects" ) {
            menu.splice(index, 1);
            }
        }
        //添加自定义菜单
        menu.push({
            title: '我的菜单 1',
            target: function () {
            alert('点击了我的菜单 1');
            }
        });
        menu.push({
            title: '我的菜单 2',
            target: function () {
            alert('点击了我的菜单 2');
            }
        });
    } else {
        menu.push({
            title: '我的菜单',
            target: function () {
            alert('点击了我的菜单');
            }
        });
    }
});
```



