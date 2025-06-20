# 注意！！
1. pip install -r requirements.txt
2. 数据集百度云链接[ShanghaiTech Dataset](https://pan.baidu.com/s/1xJnhmJbwPdnNKBM1K6F1Cg?pwd=iga3)
3. github链接[Awesome-Crowd-Counting](https://github.com/gjy3035/Awesome-Crowd-Counting)
4. 参考文档[CAN Context-Aware Crowd Counting 复现过程记录](https://blog.csdn.net/wpw5499/article/details/107807982)

    按照该文档一步步执行，一定要修改代码中报错的部分
5. SSL报错：urllib.error.URLError: <urlopen error [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: unable to get local issuer certificate (_ssl.c:1010)><br/>
    解决方案:
   1. 执行temp.py
   ```
   DefaultVerifyPaths(cafile=None, capath=None, openssl_cafile_env='SSL_CERT_FILE', openssl_cafile='C:\\Program Files\\Common Files\\ssl\\cert.pem', openssl_capath_env='SSL_CERT_DIR', openssl_capath='C:\\Program Files\\Common Files\\ssl\\certs') 
   ```
   2. 将assets/cacert.pem放在上述openssl_cafile位置
6. 如果使用的是cpu会报错AssertionError: Torch not compiled with CUDA enabled<br/>
    解决方案：
    1. 将train.py的第53、55、98、102、143、144、145、146的.cuda()改成.cpu()
    > .cuda()

    > .cpu()
7. 运行中去掉UserWarning
    1. python -W ignore::UserWarning train.py train.json val.json
    2. 或者在pycharm运行设置的Environment variables 添加
    > ;PYTHONWARNINGS=ignore::UserWarning
