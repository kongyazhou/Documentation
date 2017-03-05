# file-transfer

[cordova-plugin-file-transfer](https://github.com/apache/cordova-plugin-file-transfer)

该插件使得phonegap程序能够轻松地通过服务器上传和下载文件。

## 上传

#### 客户端Example

```javascript
// !! Assumes variable fileURL contains a valid URL to a text file on the device,
//    for example, cdvfile://localhost/persistent/path/to/file.txt

var win = function (r) {
    console.log("Code = " + r.responseCode);
    console.log("Response = " + r.response);
    console.log("Sent = " + r.bytesSent);
}

var fail = function (error) {
    alert("An error has occurred: Code = " + error.code);
    console.log("upload error source " + error.source);
    console.log("upload error target " + error.target);
}

var options = new FileUploadOptions();
options.fileKey = "file";
options.fileName = fileURL.substr(fileURL.lastIndexOf('/') + 1);
options.mimeType = "text/plain";

var params = {};
params.value1 = "test";
params.value2 = "param";

options.params = params;

var ft = new FileTransfer();
ft.upload(fileURL, encodeURI("http://some.server.com/upload.php"), win, fail, options);
```

需要设置变量fileURL的值。

我实验成功的地址为"///storage/emulated/0/DCIM/Camera/test.jpg"，具体路径该如何设置尚待研究。

更多例子见[cordova-plugin-file-transfer](https://github.com/apache/cordova-plugin-file-transfer)。

#### 服务器端

服务器端用的是php。

参见[PHP W3SCHOOL](http://www.w3school.com.cn/php/php_file_upload.asp)，其中的几个例子值得深入学习一下。

## 下载

#### 客户端

```javascript
// !! Assumes variable fileURL contains a valid URL to a path on the device,
//    for example, cdvfile://localhost/persistent/path/to/downloads/

var fileTransfer = new FileTransfer();
var uri = encodeURI("http://some.server.com/download.php");

fileTransfer.download(
    uri,
    fileURL,
    function(entry) {
        console.log("download complete: " + entry.toURL());
    },
    function(error) {
        console.log("download error source " + error.source);
        console.log("download error target " + error.target);
        console.log("upload error code" + error.code);
    },
    false,
    {
        headers: {
            "Authorization": "Basic dGVzdHVzZXJuYW1lOnRlc3RwYXNzd29yZA=="
        }
    }
);
```

更多例子见[cordova-plugin-file-transfer](https://github.com/apache/cordova-plugin-file-transfer)。

由于没有现成的服务器端，所以我采用的是《[Cordova文件传输](http://www.yiibai.com/cordova/cordova_file_transfer.html)》中的方法，即直接将uri设置为资源的地址。

这样做可能有隐私问题，资源可能能够直接通过浏览器访问得到。

需要找到解决方案。

## 参考文章

[Cordova文件传输](http://www.yiibai.com/cordova/cordova_file_transfer.html)