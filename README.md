# npmtest-hashmark

#### test coverage for  [hashmark (v4.1.0)](https://github.com/keithamus/hashmark#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-hashmark.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-hashmark) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-hashmark.svg)](https://travis-ci.org/npmtest/node-npmtest-hashmark)

#### Take contents of a file (or stdin), and output as new file with a hash in the name

[![NPM](https://nodei.co/npm/hashmark.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/hashmark)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-hashmark/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-hashmark/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-hashmark/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-hashmark/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-hashmark/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-hashmark/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-hashmark/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-hashmark/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-hashmark/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-hashmark/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-hashmark/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-hashmark/build/test-report.html](https://npmtest.github.io/node-npmtest-hashmark/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-hashmark/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-hashmark/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-hashmark/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-hashmark/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-hashmark/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-hashmark/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-hashmark/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-hashmark/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Keith Cirkel",
        "url": "http://keithcirkel.co.uk"
    },
    "bin": {
        "hashmark": "./bin/hashmark"
    },
    "bugs": {
        "url": "https://github.com/keithamus/hashmark/issues"
    },
    "config": {
        "ghooks": {
            "commit-msg": "validate-commit-msg"
        }
    },
    "dependencies": {
        "cli": "^1.0.0",
        "mkdirp": "^0.5.1"
    },
    "description": "Take contents of a file (or stdin), and output as new file with a hash in the name",
    "devDependencies": {
        "ghooks": "^1.2.1",
        "semantic-release": "^4.3.5",
        "travis-after-all": "^1.4.4",
        "validate-commit-msg": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "d2675007bbe7d566c46f358c84cf5e09326967e7",
        "tarball": "https://registry.npmjs.org/hashmark/-/hashmark-4.1.0.tgz"
    },
    "engines": {
        "node": ">0.10"
    },
    "gitHead": "55d08b9587ddaa5018af2ee8289941dbef3ef285",
    "homepage": "https://github.com/keithamus/hashmark#readme",
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "keithamus"
        }
    ],
    "name": "hashmark",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/keithamus/hashmark.git"
    },
    "scripts": {
        "semantic-release": "semantic-release pre && npm publish && semantic-release post",
        "test": "for i in $(seq 1 20); do rm -rf testdir; npm run test$i; done",
        "test1": "echo Foo | ./bin/hashmark 'test.{hash}.js' && rm test.3eae1599bb7f187b86d6427942d172ba8dd7ee5962aab03e0839ad9d59c37eb0.js",
        "test10": "echo Test1 > test.js && echo Test2 > test2.js && ./bin/hashmark -d md5 -l 4 'test*.js' '{name}-{hash}{ext}' && rm test.js test2.js test-fa02.js test2-856b.js",
        "test11": "echo Test1 > test.js && echo Test2 > test2.js && ./bin/hashmark -l 4 'test*.js' '{name}-{hash}{ext}' -m testmap.json && rm test.js test2.js test-7e5e.js test2-1a65.js testmap.json",
        "test12": "echo Test1 | ./bin/hashmark -l 4 -n test.js '{name}-{hash}{ext}' && rm test-7e5e.js",
        "test13": "echo abracadabra > test.js && ./bin/hashmark -d md5 -l 8 -r test.js '{name}-{hash}{ext}' && test ! -f test.js && rm test-97640ef5.js",
        "test14": "mkdir -p testdir/sub && echo Test1 > testdir/sub/test.js && echo Test2 > test2.js && ./bin/hashmark -d md5 -l 4 'testdir/**/*.js' 'test*.js' '{name}-{hash}{ext}' && rm testdir/sub/test.js test2.js test-fa02.js test2-856b.js && rmdir -p testdir/sub",
        "test15": "mkdir -p testdir/sub && echo Test1 > testdir/sub/test.js && echo Test2 > testdir/sub/test2.js && ./bin/hashmark -d md5 -l 4 --cwd 'testdir' 'sub/*.js' '{dir}/{name}-{hash}{ext}' && rm testdir/sub/test.js testdir/sub/test2.js testdir/sub/test-fa02.js testdir/sub/test2-856b.js && rmdir -p testdir/sub",
        "test16": "echo Foo > test.js && ./bin/hashmark -d md5 -l 8 test.js '{hash}-{base}' && rm test.js cbd8f798-test.js",
        "test17": "mkdir -p testdir/sub/nested && echo Test1 > testdir/sub/test.js && echo Test2 > testdir/sub/test2.js && ./bin/hashmark -d md5 -l 4 --cwd 'testdir' 'sub/*' '{dir}/{name}-{hash}{ext}' && rm testdir/sub/test.js testdir/sub/test2.js testdir/sub/test-fa02.js testdir/sub/test2-856b.js && rmdir -p testdir/sub/nested",
        "test18": "mkdir -p testdir/sub && echo 'Test --cwd without {dir} in pattern' > testdir/sub/test.js && echo Test2 > testdir/sub/test2.js && ./bin/hashmark -d md5 -l 4 --cwd 'testdir/sub' '*' '{name}-{hash}{ext}' && rm testdir/sub/test.js testdir/sub/test2.js testdir/sub/test-84c5.js testdir/sub/test2-856b.js && rmdir -p testdir/sub",
        "test19": "mkdir -p testdir/sub && echo 'Test --cwd and --asset-map' > testdir/sub/test.js && ./bin/hashmark -l 4 --cwd 'testdir/sub' --asset-map assets.json '*' '{name}-{hash}{ext}' && (grep -e '\"test\\.js\":\\s*\"test-7068.js\"' testdir/sub/assets.json || (echo '\nWrong content in asset-map file' 1>&2; exit 1)) && rm testdir/sub/assets.json && rm -rf testdir",
        "test2": "echo Foo | ./bin/hashmark -l 8 'test.{hash}.js' && rm test.3eae1599.js",
        "test20": "echo 'Create and write file if the directory does not exist' | ./bin/hashmark 'newtestdir/newtestsubdir/test.{hash}.js' && rm -rf newtestdir",
        "test3": "echo Bar | ./bin/hashmark -l 8 'test.{hash}.js' && rm test.842c8886.js",
        "test4": "echo Bar | ./bin/hashmark --length 8 'test.{hash}.js' && rm test.842c8886.js",
        "test5": "echo Foo | ./bin/hashmark -d md5 'test.{hash}.js' && rm test.cbd8f7984c654c25512e3d9241ae569f.js",
        "test6": "echo Foo | ./bin/hashmark --digest md5 '{hash}.js' && rm cbd8f7984c654c25512e3d9241ae569f.js",
        "test7": "echo Foo | ./bin/hashmark -d md5 -l 8  'test.{hash}.js' && rm test.cbd8f798.js",
        "test8": "echo Bar | ./bin/hashmark -d md5 -l 8  'test.{hash}.js' && rm test.962d3beb.js",
        "test9": "echo Foo > test.js && ./bin/hashmark -d md5 -l 8 test.js 'test.{hash}' && rm test.js test.cbd8f798"
    },
    "version": "4.1.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
