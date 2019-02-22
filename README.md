# CET
2018年下半年四六级准考证找回

# 说明
1. 接口来源于四六级报名网站，也就是说如果报名网站还提供准考证打印，则可以进行查询
2. UI部分借鉴了另外一个不开源的系统

# 使用方法
1. 按照依赖
```
pip install -r requirements.txt
```
2. 运行
```
python app.py # 测试环境
gunicorn -c gunc.py app:app # 用gunicorn部署
```
# 原理
1. 利用requests访问http://cet-bm.neea.edu.cn/
2. 获取验证码，利用flask提供api支持，并返回cookie
3. 提交后，下载准考证，然后解压并读取pdf用正则进行匹配即可。
4. 返回给用户

# 预览
 <img src="https://github.com/LDouble/CET/blob/master/1.jpeg" width="250"><img src="https://github.com/LDouble/CET/blob/master/2.jpeg" width="250">
