# Window下操作git

//进入bash界面

bash



//clone 到本地,使用SSH的链接

git clone xxxx.git



//查看branch和远程的仓库

git branch && git remote -v



//添加修改文件，并上传到github上

git add .

git commit

git push origin main



---

//生成Token

```
1.点击 settings
2.点击右侧的 Developer settings
3.点击 Personal access tokens(个人访问令牌)
4.点击 Generate new token
5.设置 token 信息
6.根据所需过期时间，建议设置成永远，以免麻烦，建议所有选项都选上
7.点击 Generate token 生成令牌
8.得到生成的令牌
9.应用令牌
10.修改现有的 url
git remote set-url origin  https://<your_token>@github.com/<USERNAME>/<REPO>.git
将<your_token>换成你自己得到的令牌。<USERNAME>是你自己github的用户名，<REPO>是你的项目名称
换成你自己得到的令牌。是你自己github的用户名，`是你的项目名称
然后再次执行 pull push 操作
```



//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为token

//git remote set-url origin https://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@github.com/shizeke/markdown_file.git





//更多权限的token ：`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` 

//git remote set-url origin https://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@github.com/shizeke/markdown_file.git
