# BIMBox.Viewing.API.OBVApi.getNodeIdByPath

####               通过路径获取一个对象的 nodeId。 路径是指模型树中从根节点到对象节点的名称组成的字符串，

#### 名称之间以"/"链接。 如：“北京协和医院门诊楼/3 层/KZ1”。 OBV 可以加载多个模型文件，故 nodeId 含有

#### 两个信息，一个是 modelId，用来表 示模型 ID，另一个是 dbId，用来表示在模型中的唯一对象 ID。调用 

#### OBV 的某些 API 时，需要传入 nodeId，如果只传入的 dbId，则默认取第一个模型中的 ID 为 dbId 的对

#### 象。



