php_crontab ����PHP�Ķ�ʱ���������
=============
[![Total Downloads](https://img.shields.io/packagist/dt/jenner/crontab.svg?style=flat)](https://packagist.org/packages/jenner/crontab)
[![Latest Stable Version](http://img.shields.io/packagist/v/jenner/crontab.svg?style=flat)](https://packagist.org/packages/jenner/crontab)
[![License](https://img.shields.io/packagist/l/jenner/crontab.svg?style=flat)](https://packagist.org/packages/jenner/crontab)
Ϊʲôʹ��PHP����crontab
------------
һ���ڶ�ʱ������ٵ�����£�ʹ��ԭ����crontab����һ�㲻����ʲô���⣬������ʱ����϶�ʱ�ͻ�����������⣺
+ �ı���ʽ�Ķ�ʱ����ɶ��Ժܲ��û���κ�ע�͵�����£����˺����ڲ���Դ���������˽ⶨʱ�����ҵ���߼�
+ �ڷֲ�ʽ�ĳ����У���ʱ�����ɢ�䵽��̨�����ϣ��޷�ͳһ����
+ ��ʱ�������־���ܼ��л������Զ�ʱ��������з����������ų��Ƚ��鷳
+ ��ͬ�û��µĶ�ʱ������Ҫ�ֿ���д���ɶ��ԡ���ά���Բ�
�������ϼ���ԭ���������е���Ҫһ�����Լ��л�����ġ������õĶ�ʱ���������

����
-----------
+ ��ʱ������Բ��������ı���ʽ����ʽ���ڣ����Դ洢�ڻ��塢���ݿ��У���������Կ��������ܣ��ں�̨�Զ�ʱ������б༭
+ ��ʱ�������־�ǿ����õģ�����԰���ҵ�����󣬶���־���в��컯����
+ crontab�����ڲ�ͬ�û��µĶ�ʱ������Ҫ�ֿ���д��ʹ��php_crontab����󣬿��Լ������ýű�ִ��Ȩ��

ʹ�÷�ʽ���£�
+ ��дһ��������������ɲο�test/simple.php
+ �������ű���ӵ�crontab�У�һ����ִ��һ��

����
-----------
+ ���ö���̣�һ������Ϊһ�����̣��������ִ���ӳ�����
+ ֧���趨�û����û���
+ ֧���趨���ִ��ʱ��
+ ֧������ض���
+ ����libev��ʱ���¼�������֧���ػ�����

�����ͨ�����·�ʽʵ�ֲַ�ʽ��ʱ�������
------------
+ ��ʱ����������Ϣд��redis�����Ⱥ��ʹ�ö��Ļ����Զ��ַ�
+ ��ʱ����д���ļ����޸�ʱrsyncͬ��
+ д��mysql���ݿ⣨�Ƽ����Ӽܹ������Զ�ͬ��

TODO
-------------
+ ����HTTP����
+ ����reload����


**����crontab���У�**
```shell
* * * * * php demo.php
```
```php
<?php
$crontab_config = [
    'test_1' => [
        'name' => '������1', //��������
        'cmd' => 'php -v', //��Ҫִ�е�cli����
        'output' => '/tmp/test.log', //����ض����ļ�
        'time' => '* * * * *', //��ʱ����ʱ�����ã���crontab����
        'user_name' => 'www', //cli�������е��û����
        'group_name' => 'group_name', //cli�������е��û������
    ],
    'single_test' => [
        'name' => 'php -i',
        'cmd' => 'php -i',
        'output' => '/tmp/single_script.log',
        'time' => [
            '* * * * *',
            '* * * * *',
        ],
    ],
];

$time = time();
$crontab_server = new \Jenner\Zebra\Crontab\Crontab($crontab_config);
$crontab_server->start($time);
```
**������������**

ÿ���Ӵ���һ��
```php
$crontab_config = [
    'test_1' => [
        'name' => '������1',
        'cmd' => 'php -r "echo "11111" . PHP_EOL;sleep(60);"',
        'output' => '/www/test.log',
        'time' => '* * * * *',
        'user_name' => 'www',
        'group_name' => 'www'
    ],
    'single_test' => [
        'name' => 'php -i',
        'cmd' => 'php -i',
        'output' => '/tmp/single_script.log',
        'time' => [
            '* * * * *',
            '* * * * *',
        ],
    ],
];

$daemon = new \Jenner\Zebra\Crontab\Daemon($crontab_config, "logfile.log");
$daemon->start();
```


���߶�С�����ܾ���
-----------
�ڷֲ�ʽ�����У�����԰Ѷ�ʱ����д�����ݿ��н���ͳһ����������趨��Щ��ʱ����������Щ����ִ�У�
Ȼ��ͨ�������ı��ļ��ķ�ʽ���͵����л����ϣ�������Щ�����ϵ�phpCrontab��ȡ�����Ӷ�ʵ�ֲַ�ʽ�����µĶ�ʱ����ͳһ����


[���͵�ַ:www.huyanping.cn](http://www.huyanping.cn/ "����Գʼ�ղ���")



