# git commit message
git commit message规范指提交代码时编写的规范注释，编写良好的Commit messages可以达到3个重要的目的：

* 加快代码review的流程
* 帮助我们编写良好的版本发布日志
* 让之后的维护者了解代码里出现特定变化和feature被添加的原因

# Angular Git Commit Guidelines
业界应用的比较广泛的是Angular Git Commit Guidelines：

`<type>(<scope>): <subject>`</br>
`<BLANK LINE>`</br>
`<body>`</br>
`<BLANK LINE>`</br>
`<footer>`</br>
|name|description|
|-|-|
|type|提交类型|
|scope|可选项，本次 commit 波及的范围|
|subject|简明扼要的阐述下本次 commit 的主旨，在Angular Git Commit Guidelines中强调了三点。使用祈使句，首字母不要大写，结尾无需添加标点|
|body|同样使用祈使句，在主体内容中我们需要把本次 commit 详细的描述一下，比如此次变更的动机|
|footer|描述下与之关联的 issue 或 break change|

# 简易版
项目中实际可以采用简易版规范：
`<type>(<scope>):<subject>`
# type规范
Angular Git Commit Guidelines中推荐的type类型如下：
|type|description|
|-|-|
|feat|新增功能|
|fix|修复bug|
|docs|仅文档更改|
|style|不影响代码含义的更改（空白、格式设置、缺失 分号等）|
|refactor|既不修复bug也不添加特性的代码更改|
|perf|改进性能的代码更改|
|test|添加缺少的测试或更正现有测试|
|chore|对构建过程或辅助工具和库（如文档）的更改|
|delete|删除功能或文件|
|modify|修改功能|
|build|改变构建流程，新增依赖库、工具等（例如webpack、gulp、npm修改）|
|test|测试用例的新增、修改|
|ci|自动化流程配置修改|
|revert|回滚到上一个版本|

# 单次提交注意事项
* 提交问题必须为同一类别
* 提交问题不要超过3个
* 提交的commit发现不符合规范，git commit --amend -m "新的提交信息"或 git reset --hard HEAD 重新提交一次