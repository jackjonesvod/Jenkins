Jenkins中的常用的变量

## Jenkins 内置环境变量（系统自动提供）

这些变量不用声明，直接可以用。常见的有：

变量名	说明	示例
env.BUILD_NUMBER	构建号（流水线每次执行递增）	15
env.BUILD_ID	构建 ID（时间戳格式）	2025-09-28_07-21-59
env.BUILD_TAG	唯一标识构建	jenkins-myjob-15
env.JOB_NAME	Job 的完整名称	myproject/myjob
env.JOB_BASE_NAME	Job 名称（不带路径）	myjob
env.BUILD_URL	构建的 URL	http://jenkins:8080/job/myjob/15/
env.JENKINS_URL	Jenkins 的根地址	http://jenkins:8080/
env.WORKSPACE	工作目录	/var/lib/jenkins/workspace/myjob
env.NODE_NAME	执行的节点名称	linux-node1
env.EXECUTOR_NUMBER	当前节点的 Executor 编号	0
env.GIT_BRANCH	Git 分支名（需 git 插件支持）	main
env.GIT_COMMIT	Git 提交哈希（需 git 插件支持）	a1b2c3d4

👉 这些变量 Jenkins 会自动注入，你随时可以在 sh 或 echo 里使用，比如：

echo "构建号: ${env.BUILD_NUMBER}"
echo "Git 分支: ${env.GIT_BRANCH}"
