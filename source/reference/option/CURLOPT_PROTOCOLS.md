## 声明

```
CURLcode curl_easy_setopt(CURL *handle, CURLOPT_PROTOCOLS, long bitmask);
```

## 概要

设置允许使用的协议。

## 详情

传入一个`long`，这个参数持有`CURLPROTO_*`定义的位掩码。如果使用了该选项，这个位掩码限制了libcurl在传输时能使用的协议。这允许你可以有一个广泛支持各种协议的libcurl构建版本，但仍然可以限制特定的传输只允许使用这些协议的一个子集。默认情况下libcurl会接受所有它支持的协议（`CURLPROTO_ALL`）。参考`CURLOPT_REDIR_PROTOCOLS`。

下面是可用的协议定义：
```
CURLPROTO_DICT
CURLPROTO_FILE
CURLPROTO_FTP
CURLPROTO_FTPS
CURLPROTO_GOPHER
CURLPROTO_HTTP
CURLPROTO_HTTPS
CURLPROTO_IMAP
CURLPROTO_IMAPS
CURLPROTO_LDAP
CURLPROTO_LDAPS
CURLPROTO_POP3
CURLPROTO_POP3S
CURLPROTO_RTMP
CURLPROTO_RTMPE
CURLPROTO_RTMPS
CURLPROTO_RTMPT
CURLPROTO_RTMPTE
CURLPROTO_RTMPTS
CURLPROTO_RTSP
CURLPROTO_SCP
CURLPROTO_SFTP
CURLPROTO_SMB
CURLPROTO_SMTP
CURLPROTO_SMTPS
CURLPROTO_TELNET
CURLPROTO_TFTP
```

## 默认值

所有内置的协议。

## 适用协议

所有协议。

## 可用性

在7.19.4加入。

## 返回值

如果支持该选项，返回`CURLE_OK`；否则返回`CURLE_UNKNOWN_OPTION`。