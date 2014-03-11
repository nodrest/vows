Vows
====

> 为node.js的异步BDD([行为驱动开发(Behaviour Driven Development)][BDD])和连续测试

#### <http://vowsjs.org> #

介绍
------------
There are two reasons why we might want asynchronous testing. The first, and obvious reason is that node.js is asynchronous, and therefore our tests need to be. The second reason is to make test suites which target I/O libraries run much faster.

_Vows_ is an experiment in making this possible, while adding a minimum of overhead.

简介
--------

    var vows = require('vows'),
        assert = require('assert');

    vows.describe('Deep Thought').addBatch({
        'An instance of DeepThought': {
            topic: new DeepThought,

            'should know the answer to the ultimate question of life': function (deepThought) {
                assert.equal (deepThought.question('what is the answer to the universe?'), 42);
            }
        }
    });

覆盖率报告
------------------
Code coverage reporting is available if _instrumented_ code is detected.  Currently only _instrumentation_ via [node-jscoverage][] is supported.  When _instrumented_ code is detected and coverage reporting is enabled using any of the `--cover-plain`, `--cover-html`, or `--cover-json` options a code coverage map is generated.

### 下载安装 [node-jscoverage][]
[node-jscoverage][]需要从源码编译的二进制包:

    $ git clone https://github.com/visionmedia/node-jscoverage.git
    $ cd node-jscoverage/
    $ ./configure
    checking for a BSD-compatible install... /usr/bin/install -c
    checking whether build environment is sane... yes
    [...]
    $ make && sudo make install

这里介绍了[jscoverage][]

### 与jscoverage插装

    $ jscoverage myfile.js myfile-instrumented.js
    
安装
------------

    $ npm install vows

文档
-------------

Head over to <http://vowsjs.org>

运行测试
-------------

```
  npm test
```

作者
-------

Alexis Sellier <<alexis@cloudhead.io>>, Charlie Robbins,

*...and many others*

[BDD]:http://zh.wikipedia.org/wiki/%E8%A1%8C%E4%B8%BA%E9%A9%B1%E5%8A%A8%E5%BC%80%E5%8F%91
[jscoverage]:http://blog.csdn.net/testing_is_believing/article/details/2100886
[node-jscoverage]:https://github.com/visionmedia/node-jscoverage
