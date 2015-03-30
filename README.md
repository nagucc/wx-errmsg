# wx-errmsg
微信全局返回码

## 目的
当我们使用微信API时，返回值是这样的结构：

```
{
   "errcode": 0,
   "errmsg": "created",
}
```
其中：
*errcode* 是返回码， *errmsg* 是相应的信息。

当出现错误的时候，我们需要对用户给出错误提示，如果我们直接将*errmsg*的值返回给用户，这样用户体验是不好的。
然而，微信API的全局返回码数量众多，如果我们针对不同的错误给出提示，这将是一个工作量极大的任务。
为了能够提供用户体验较好的错误提示，同时也减轻码农的工作量，我们将官方提供的全局返回码说明封装为对象，让码农们可以根据错误代码直接返回友(zhong)好(wen)的错误提示。

## 安装
`npm install wx-errmsg`


## 用法

```
wxerr = requrie('wx-errmsg');

wxerr['0']; // => '请求成功'
wxerr['60112']; // => '成员姓名不合法'

```
