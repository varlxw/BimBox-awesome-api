> # BIMBox.Viewing.API.initializeViewer
>
> ---

#### 将 OBV 视图嵌入到自己的页面中。初始化一个OBV视图并加载指定模型

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| containerld | string | 页面view容器的id |
| options | object | view配置 |
| undefined |  |  |
| callback | function | 回调函数传出API |

第二个参数 options

```js
const options = {
    shouldInitializeAuth: this.shouldInitializeAuth,
    env: this.env, // OBV 的运行环境。 Production：生产环境， Staging：试验环境
    getAccessToken: getToken ? getAccessToken : undefined, // 获取 Token 的回调，一个页面中只需要获取一次即可
    refreshToken: getToken ? getAccessToken : undefined, // 刷新 Token 的回调，后台 API 可以提供刷新 Token的函数，而不是使用获取 Token 的函数。
    documentId: this.urn, // 如果加载多个模型，需使用逗号隔开每个 urn。
    globalOffset: this.globalOffset, // 指定模型的位置。如果多个模型，则以逗号隔开；必须与 documentId 指定的模型个数一致。
    fullscreen: this.fullscreen // true 是全屏 false 是非全屏
 }
```



