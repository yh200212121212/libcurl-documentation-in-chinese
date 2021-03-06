## 声明

```
CURLcode curl_easy_setopt(CURL *handle, CURLoption option, parameter);
```

## 概要

设置一个easy句柄的选项。

## 详情

`curl_easy_setopt`用来告诉libcurl如何运作。通过设置适当的选项，应用程序可以改变libcurl的行为。所有选项都通过一个`option`以及后面的一个`parameter`来设置。根据指定选项的期望，参数可以是一个`long`，一个函数指针，一个对象指针或者一个`curl_off_t`。要小心地阅读本手册，因为错误的输入值可能会导致libcurl严重损坏！你可以只在每次函数调用时设置一个选项。一个典型的应用程序在配置阶段调用许多次`curl_easy_setopt`。

通过该函数设置的选项对这个句柄上所有后续的传输都有效。选项不会在每次传输之间以任何方式重新设置，所以如果你希望接下来的传输使用不同的选项，你必须在每次传输之间修改它们。你可以通过`curl_easy_reset`把所有选项重设回内部的默认值。

字符串以`char*`参数传递给libcurl，并且会被libcurl复制。因此指针参数指向的字符串内存空间在`curl_easy_setopt`返回之后可以被覆写。这个规则唯一的例外是`CURLOPT_POSTFIELDS`，不过另一个会复制字符串的`CURLOPT_COPYPOSTFIELDS`有一些用法特点，你需要阅读一下。

在7.17.0版本以前，字符串是不会被复制的。所以用户被迫保留这些字符串，直到libcurl不再需要它们。

`handle`参数是调用`curl_easy_init`或者`curl_easy_duphandle`的返回值。

## 行为选项

### CURLOPT_VERBOSE

显示详细的信息。参考[CURLOPT_VERBOSE](../option/CURLOPT_VERBOSE.md)。

### CURLOPT_HEADER

在正文输出中包含头部。参考[CURLOPT_HEADER](../option/CURLOPT_HEADER.md)。

### CURLOPT_NOPROGRESS

关闭进度计量。参考[CURLOPT_NOPROGRESS](../option/CURLOPT_NOPROGRESS.md)。

### CURLOPT_NOSIGNAL

不要安装信号处理器。参考[CURLOPT_NOSIGNAL](../option/CURLOPT_NOSIGNAL.md)。

### CURLOPT_WILDCARDMATCH

根据一个文件名匹配模式传输多个文件。参考[CURLOPT_WILDCARDMATCH](../option/CURLOPT_WILDCARDMATCH.md)。

## 回调选项

### CURLOPT_WRITEFUNCTION

写数据的回调。参考[CURLOPT_WRITEFUNCTION](../option/CURLOPT_WRITEFUNCTION.md)。

### CURLOPT_WRITEDATA

传递给写数据回调的数据指针。参考[CURLOPT_WRITEDATA](../option/CURLOPT_WRITEDATA.md)。

### CURLOPT_READFUNCTION

读数据的回调。参考[CURLOPT_READFUNCTION](../option/CURLOPT_READFUNCTION.md)。

### CURLOPT_READDATA

传递给读数据回调的数据指针。参考[CURLOPT_READDATA](../option/CURLOPT_READDATA.md)。

### CURLOPT_IOCTLFUNCTION

I/O操作的回调。参考[CURLOPT_IOCTLFUNCTION](../option/CURLOPT_IOCTLFUNCTION.md)。

### CURLOPT_IOCTLDATA

传递给I/O操作回调的数据指针。参考[CURLOPT_IOCTLDATA](../option/CURLOPT_IOCTLDATA.md)。

### CURLOPT_SEEKFUNCTION

重定位操作的回调。参考[CURLOPT_SEEKFUNCTION](../option/CURLOPT_SEEKFUNCTION.md)。

### CURLOPT_SEEKDATA

传递给重定位操作回调的数据指针。参考[CURLOPT_SEEKDATA](../option/CURLOPT_SEEKDATA.md)。

### CURLOPT_SOCKOPTFUNCTION

`sockopt`操作的回调。参考[CURLOPT_SOCKOPTFUNCTION](../option/CURLOPT_SOCKOPTFUNCTION.md)。

### CURLOPT_SOCKOPTDATA

传递给`sockopt`回调的数据指针。参考[CURLOPT_SOCKOPTDATA](../option/CURLOPT_SOCKOPTDATA.md)。

### CURLOPT_OPENSOCKETFUNCTION

创建套接字的回调。参考[CURLOPT_OPENSOCKETFUNCTION](../option/CURLOPT_OPENSOCKETFUNCTION.md)。

### CURLOPT_OPENSOCKETDATA

传递给创建套接字回调的数据指针。参考[CURLOPT_OPENSOCKETDATA](../option/CURLOPT_OPENSOCKETDATA.md)。

### CURLOPT_CLOSESOCKETFUNCTION

关闭套接字的回调。参考[CURLOPT_CLOSESOCKETFUNCTION](../option/CURLOPT_CLOSESOCKETFUNCTION.md)。

### CURLOPT_CLOSESOCKETDATA

传递给关闭套接字回调的数据指针。参考[CURLOPT_CLOSESOCKETDATA](../option/CURLOPT_CLOSESOCKETDATA.md)。

### CURLOPT_PROGRESSFUNCTION

已废弃的进度计量回调。参考[CURLOPT_PROGRESSFUNCTION](../option/CURLOPT_PROGRESSFUNCTION.md)。

### CURLOPT_PROGRESSDATA

传递给已废弃的进度计量回调的数据指针。参考[CURLOPT_PROGRESSDATA](../option/CURLOPT_PROGRESSDATA.md)。

### CURLOPT_XFERINFOFUNCTION

进度计量回调。参考[CURLOPT_XFERINFOFUNCTION](../option/CURLOPT_XFERINFOFUNCTION.md)。

### CURLOPT_XFERINFODATA

传递给进度计量回调的数据指针。参考[CURLOPT_XFERINFODATA](../option/CURLOPT_XFERINFODATA.md)。

### CURLOPT_HEADERFUNCTION

写头部的回调。参考[CURLOPT_HEADERFUNCTION](../option/CURLOPT_HEADERFUNCTION.md)。

### CURLOPT_HEADERDATA

传递给写头部回调的数据指针。参考[CURLOPT_HEADERDATA](../option/CURLOPT_HEADERDATA.md)。

### CURLOPT_DEBUGFUNCTION

调试信息的回调。参考[CURLOPT_DEBUGFUNCTION](../option/CURLOPT_DEBUGFUNCTION.md)。

### CURLOPT_DEBUGDATA

传递给调试信息回调的数据指针。参考[CURLOPT_DEBUGDATA](../option/CURLOPT_DEBUGDATA.md)。

### CURLOPT_SSL_CTX_FUNCTION

SSL上下文逻辑的回调。参考[CURLOPT_SSL_CTX_FUNCTION](../option/CURLOPT_SSL_CTX_FUNCTION.md)。

### CURLOPT_SSL_CTX_DATA

传递给SSL上下文回调的数据指针。参考[CURLOPT_SSL_CTX_DATA](../option/CURLOPT_SSL_CTX_DATA.md)。

### CURLOPT_CONV_TO_NETWORK_FUNCTION

本机编码转换成网络编码的回调。参考[CURLOPT_CONV_TO_NETWORK_FUNCTION](../option/CURLOPT_CONV_TO_NETWORK_FUNCTION.md)。

### CURLOPT_CONV_FROM_NETWORK_FUNCTION

网络编码转换成本机编码的回调。参考[CURLOPT_CONV_FROM_NETWORK_FUNCTION](../option/CURLOPT_CONV_FROM_NETWORK_FUNCTION.md)。

### CURLOPT_CONV_FROM_UTF8_FUNCTION

UTF-8编码转换成本机编码的回调。参考[CURLOPT_CONV_FROM_UTF8_FUNCTION](../option/CURLOPT_CONV_FROM_UTF8_FUNCTION.md)。

### CURLOPT_INTERLEAVEFUNCTION

RTSP交叉数据回调。参考[CURLOPT_INTERLEAVEFUNCTION](../option/CURLOPT_INTERLEAVEFUNCTION.md)。

### CURLOPT_INTERLEAVEDATA

传递给RTSP交换回调的数据指针。参考[CURLOPT_INTERLEAVEDATA](../option/CURLOPT_INTERLEAVEDATA.md)。

### CURLOPT_CHUNK_BGN_FUNCTION

数据块的通配符下载开始的回调。参考[CURLOPT_CHUNK_BGN_FUNCTION](../option/CURLOPT_CHUNK_BGN_FUNCTION.md)。

### CURLOPT_CHUNK_END_FUNCTION

数据块的通配符下载结束的回调。参考[CURLOPT_CHUNK_END_FUNCTION](../option/CURLOPT_CHUNK_END_FUNCTION.md)。

### CURLOPT_CHUNK_DATA

传递给数据块回调的数据指针。参考[CURLOPT_CHUNK_DATA](../option/CURLOPT_CHUNK_DATA.md)。

### CURLOPT_FNMATCH_FUNCTION

通配符匹配的回调。参考[CURLOPT_FNMATCH_FUNCTION](../option/CURLOPT_FNMATCH_FUNCTION.md)。

### CURLOPT_FNMATCH_DATA

传递给通配符匹配回调的数据指针。参考[CURLOPT_FNMATCH_DATA](../option/CURLOPT_FNMATCH_DATA.md)。

## 错误选项

### CURLOPT_ERRORBUFFER

错误消息缓冲区。参考[CURLOPT_ERRORBUFFER](../option/CURLOPT_ERRORBUFFER.md)。

### CURLOPT_STDERR

替换stderr的流。参考[CURLOPT_STDERR](../option/CURLOPT_STDERR.md)。

### CURLOPT_FAILONERROR

在出现HTTP的4xx错误时失败。参考[CURLOPT_FAILONERROR](../option/CURLOPT_FAILONERROR.md)。

## 网络选项

### CURLOPT_URL

设置使用的URL。参考[CURLOPT_URL](../option/CURLOPT_URL.md)。

### CURLOPT_PATH_AS_IS

禁止压缩路径中的`/../`和`/./`序列。参考[CURLOPT_PATH_AS_IS](../option/CURLOPT_PATH_AS_IS.md)。

### CURLOPT_PROTOCOLS

设置允许使用的协议。参考[CURLOPT_PROTOCOLS](../option/CURLOPT_PROTOCOLS.md)。

### CURLOPT_REDIR_PROTOCOLS

允许重定向的协议。参考[CURLOPT_REDIR_PROTOCOLS](../option/CURLOPT_REDIR_PROTOCOLS.md)。