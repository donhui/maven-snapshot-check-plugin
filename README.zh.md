# Maven SNAPSHOT Check Plugin

[![Build Status](https://ci.jenkins.io/buildStatus/icon?job=Plugins%2Fmaven-snapshot-check-plugin%2Fmaster)](https://ci.jenkins.io/job/Plugins/job/maven-snapshot-check-plugin/job/master/)
[![Jenkins Plugin](https://img.shields.io/jenkins/plugin/v/maven-snapshot-check.svg)](https://plugins.jenkins.io/maven-snapshot-check)
[![Jenkins Plugin Installs](https://img.shields.io/jenkins/plugin/i/maven-snapshot-check.svg?color=blue)](https://plugins.jenkins.io/maven-snapshot-check)

该插件用来检查 pom.xml 是否包含 SNAPSHOT。


# 使用

## 自由风格 job 使用

在 `构建` 区域，增加 `Maven SNAPSHOT Check` 构建步骤

![add-build-step](images/add-build-step.png)

如果勾选了复选框，它将检查 pom.xml 中是否包含 SNAPSHOT。

![maven-snapshot-check-plugin-usage](images/maven-snapshot-check-plugin-usage.png)

如果匹配，该次构建将被标记为失败。

![job-build-console-output](images/job-build-console-output.png)

## 流水线 job 使用
```
step([$class: 'MavenSnapshotCheck', check: 'true'])
```
或者
```
mavenSnapshotCheck check: 'true'
```

# Bug 报告
请在 https://github.com/jenkinsci/maven-snapshot-check-plugin/issues 提交 bug 报告或新功能请求。

# 如何构建及测试？
* 构建插件：

`mvn package`

* 本地测试（调用本地附带了该插件的 Jenkins 实例）；

`mvn hpi:run`

更多详情请参考 https://jenkinsci.github.io/maven-hpi-plugin/ 。
