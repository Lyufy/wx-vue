### Express中接入vue
进入express项目的静态文件根目录public文件夹

13、创建基于webpack模版的项目 vue_prj  (任意命名项目名称vue_prj)

 　　vue init webpack vue_prj

14、进入项目 vue_prj 文件夹

　　cd vue_prj

15、安装vue项目依赖

　　npm install

16、（可选）测试并运行vue前端项目，在浏览器上输入localhost:8080，检查基于vue-cli脚手架的项目是否创建完成

　　npm run dev

 17、每次改动 vue_prj 里的文件之后，均要执行一次 build

　　npm run build

18、将express项目的服务器静态文件根目录 指向 vue 执行build后的输出文件夹 dist

　　修改app.js文件里的代码如下
　　app.use(express.static(path.join(__dirname, 'public/vue_prj/dist')));