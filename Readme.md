## zhontai前端代码生成器
配合后端使用：https://github.com/share36/Admin.Core.Dev

## 使用
- 复制 gen/gen-dev-api.js 到项目，添加package.json命令：`"gen:dev:api": "node ./gen/gen-dev-api"`,执行`npm run gen:dev:api`生成dev模块接口定义
- 将src/views/dev添加到项目src/views文件夹
- 修改/src/router/route.ts,将生成器节点添加到 '/example'前面即可
  ```js
  [
        {
          path: '/dev',
          name: 'dev',
          redirect: '/dev/codegen',
          meta: {
            title: '生成器',
            isLink: '',
            isHide: false,
            isKeepAlive: true,
            isAffix: false,
            isIframe: false,
            roles: ['admin'],
            icon: 'iconfont icon-zujian',
          },
          children: [
            {
              path: '/dev/codegen',
              name: '/dev/codegen',
              component: () => import('/@/views/dev/codegen/index.vue'),
              meta: {
                title: '代码生成',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                roles: ['admin'],
                icon: 'iconfont icon-zujian',
              },
            }]
        },
        //...{path: '/example',...}
  ]
  ```