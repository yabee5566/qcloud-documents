### 授权子帐号拥有特定的主题模型的消息队列的读权限

企业帐号CompanyExample（ownerUin为12345678）有一个基于主题模型的消息队列，同时他有一个子账号Developer，希望其可以访问该消息队列。

step1：通过策略语法方式创建以下策略
```
{
    "version": "2.0",
    "statement":   
     {
        "action": "cmqqueue:SendMessage",
        "resource":"qcs::cmqqueue:::queueName/uin/12345678/test-caten",
        "effect": "allow"
     } 
}
```

step2：将该策略授权给子账号。授权方式请参考[授权管理](https://cloud.tencent.com/document/product/378/8961)。
