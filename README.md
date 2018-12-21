# rongyun-thinkphp5
thinkphp5整合融云SDK

下载融云官方SDK放入extend文件夹下

默认SDK没有命名空间，自己修改并加入命名空间(Rongyun)

修改文件路径，统一放入rongyun文件夹下(防止报not found错误)

测试demo
````
public function send_msg()
{
    $appkey = '你的KEY';
    $appSecret = '你的秘钥';
    $rong_yun = new \Rongyun\RongCloud($appkey, $appSecret);

    $content = [
        'content' => 'thisisapush'
    ];
    $res = $rong_yun->Message()->publishPrivate(41732, [40036], 'RC:TxtMsg',json_encode($content), 'thisisapush', '{\"pushData\":\"hello\"}', '4', '0', '0', '0', '0');
    dump($res);
}
````
返回结果

````
string(12) "{"code":200}"
````

```
Author: gzy
QQ: 1113075326
```
