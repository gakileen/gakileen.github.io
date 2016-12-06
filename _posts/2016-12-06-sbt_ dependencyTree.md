Maven 项目中可以用 `dependency:tree`来显示依赖树，而 sbt 是借助于 ivy 来管理项目依赖。sbt 项目可以用三种方式来显示项目依赖，分别是：Shell 脚本, 自定义 sbt 任务, 和 sbt-dependency-plugin 方式。最后一种方式最强大也是最简单，本文只介绍这种。


#### sbt插件显示依赖树
可以在 ~/.sbt/0.13/plugins/plugins.sbt 或项目中新建 project/plugins.sbt 中加入行

```
addSbtPlugin("net.virtual-void" % "sbt-dependency-graph" % "0.8.2")
```

这时在 sbt 的控制台下就增加了好多任务,

```
dependencyTree: Shows an ASCII tree representation of the project's dependencies
dependencyBrowseGraph: Opens a browser window with a visualization of the dependency graph (courtesy of graphlib-dot + dagre-d3).
dependencyGraph: Shows an ASCII graph of the project's dependencies on the sbt console
dependencyList: Shows a flat list of all transitive dependencies on the sbt console (sorted by organization and name)
whatDependsOn <organization> <module> <revision>: Find out what depends on an artifact. Shows a reverse dependency tree for the selected module.
dependencyLicenseInfo: show dependencies grouped by declared license
dependencyStats: Shows a table with each module a row with (transitive) Jar sizes and number of dependencies
dependencyGraphMl: Generates a .graphml file with the project's dependencies to target/dependencies-<config>.graphml. Use e.g. yEd to format the graph to your needs.
dependencyDot: Generates a .dot file with the project's dependencies to target/dependencies-<config>.dot. Use graphviz to render it to your preferred graphic format.
ivyReport: let's ivy generate the resolution report for you project. Use show ivyReport for the filename of the generated report
```

 dependencyTree(显示像  Maven 的  dependency:tree 那样) 和 dependencyBrowseGraph(打开浏览器显示一个依赖关系图)
 
 
 参考：http://unmi.cc/show-sbt-dependency-tree/?utm_source=tuicool&utm_medium=referral