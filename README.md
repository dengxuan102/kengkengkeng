项目中遇到的小坑
坑一：
2019/07/30：
    问题：vue+elementui的项目，打包后elementui组件的字体图标不能正常显示的问题，
    解决：在build目录下utils.js文件中添加配置项，
    if (options.extract) {
      return ExtractTextPlugin.extract({
        use: loaders,
        fallback: 'vue-style-loader',
        publicPath: '../../'    //添加的配置项
      })
    } else {
      return ['vue-style-loader'].concat(loaders)
    }
  }
