Glossary
Use this only when a concise explanation would help the user stay oriented.
Do not paste this as a glossary unless the user asks.

General
frontend: 用户直接看到和操作的界面部分
backend: 用户看不见、负责数据和业务逻辑的服务部分
API: 前端和后端互相说话的接口
database: 存数据的地方
cache: 临时存一份数据，让系统更快
schema: 数据应该长什么样的约定
state: 页面或程序当前记住的状态
component: 页面里可复用的一块界面
hook: React 里复用状态或逻辑的函数
props: 父组件传给子组件的数据
middleware: 请求到达真正处理逻辑前先经过的一层处理
Debugging
bug: 程序行为和预期不一致的问题
stack trace: 报错沿着哪条调用路径冒出来
exception: 程序运行时抛出的错误
undefined: 这个值没有被定义
null: 这里明确是空值
timeout: 等太久没有结果，系统放弃了
retry: 失败后再试一次
fallback: 主方案失败时的备用方案
race condition: 两件事先后顺序不稳定，导致结果偶尔出错
CORS: 浏览器因为安全规则拦住了跨网站请求
hydration: 页面从服务端结果接到浏览器交互状态的过程
Verification
test: 检查功能行为是否符合预期
lint: 检查代码风格和容易出错的写法
build: 确认项目能被正式打包运行
typecheck: 检查数据类型是否对得上
CI: GitHub 等平台自动跑检查的流程
snapshot: 保存一份输出结果，用来对比以后有没有变化
Git
repository: 代码仓库，存放项目和历史记录
branch: 一条独立的修改线
commit: 把这次修改保存成一个版本点
diff: 查看这次具体改了哪些内容
merge: 把两条修改线合到一起
rebase: 把自己的修改重新整理到最新主线上
conflict: 两边改了同一个地方，Git 不知道该听谁的
stash: 临时把手头修改收起来
revert: 新增一次反向修改，把之前的效果撤掉
reset: 把历史或文件状态退回去，可能有风险
push: 把本地提交上传到远程仓库
pull: 从远程仓库拉取最新代码
Deployment
deploy: 把网站或应用发布到可访问的环境
staging: 正式上线前的预演环境
production: 真实用户正在使用的正式环境
environment variable: 不写进代码、由环境提供的配置值，常用来放密钥
secret: 密钥、token、密码等不能公开的敏感信息
migration: 改数据库结构或数据的脚本
Product Implementation
MVP: 最小可用版本，先验证核心目标
pagination: 分页加载，避免一次展示太多数据
rate limit: 限制请求频率，防止服务被刷爆
responsive: 界面能适配不同屏幕
accessibility: 让更多用户，包括使用辅助工具的人，也能顺利使用
auth: 登录鉴权，确认用户是谁以及能做什么
queue: 把任务排队处理，避免同时太多请求挤爆系统
