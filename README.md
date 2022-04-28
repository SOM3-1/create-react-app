# create-react-app
- npm init
- npm install react react-dom react-router-dom formik yup history rxjs
- npm install @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli webpack-dev-server html-webpack-plugin path --save-dev
-- scripts : 
```
"start": "react-scripts start",
"build": "react-scripts build",
"test": "react-scripts test",
"eject": "react-scripts eject"
```
- webpack.config.js File
```
js
var HtmlWebpackPlugin = require('html-webpack-plugin');
const path = require('path');
module.exports = {
    mode: 'development',
    resolve: {
        extensions: ['.js', '.jsx']
    },
    module: {
        rules: [
            {
                test: /\.jsx?$/,
                loader: 'babel-loader'
            }
        ]
    },
    resolve: {
        extensions: ['.js', '.jsx'],
        alias: {
            '@': path.resolve(__dirname, 'src/'),
        }
    },
    plugins: [new HtmlWebpackPlugin({
        template: './src/index.html'
    })],
    devServer: {
        historyApiFallback: true
    },
    externals: {
        // global app config object
        config: JSON.stringify({
            apiUrl: 'http://localhost:4000'
        })
    }
}
```
- .babelrc
 ```
js
{
    "presets": [
        "@babel/preset-react",
        "@babel/preset-env"
    ]
}
```

