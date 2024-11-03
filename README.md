## 【文章备份】微信PC测试版 v4.0.0.26 防撤回

在新鲜出炉的微信 4.0 测试版中找到了简陋的实现防撤回的方法。

**<mark>仅供学习研究，请务必于阅读 24h 后忘记它（笑）。</mark>**

极大地参考了：<br>
https://github.com/huiyadanli/RevokeMsgPatcher/wiki/微信防撤回与多开教程

修补好的文件，可以替换原文件使用：<br>
https://zeta.lanzouq.com/b0nykpxqh?pwd=zeta

1. 用 x64dbg 附加微信
   <img width="1092" alt="Snipaste_2024-11-04_01-46-11" src="https://github.com/user-attachments/assets/dd1be7f0-b360-4d7c-b081-7c5b46b5e7ee">

2. 在 符号 选项卡中，双击进入 Weixin.dll
   <img width="1092" alt="Snipaste_2024-11-04_01-47-50" src="https://github.com/user-attachments/assets/03197df0-c76d-4889-beef-7bd98ca2ee1d">

3. 右键搜索 - 当前区域 - 字符串
   <img width="1092" alt="Snipaste_2024-11-04_01-50-09" src="https://github.com/user-attachments/assets/438e8412-dad8-4afa-932e-9d1adf9db04f">

4. 搜索关键字 revokemsg 双击进入
   <img width="1092" alt="Snipaste_2024-11-04_01-52-09" src="https://github.com/user-attachments/assets/4e0b8489-1a62-428c-bab1-dc6adf9870d1">

5. 要修改的是它上方的这行 jne 判断跳转
   <img width="1092" alt="Snipaste_2024-11-04_01-54-57" src="https://github.com/user-attachments/assets/ed65250a-b30b-4f84-882a-e89111679cba">

6. 点击空格修改，将 jnz 改为 jmp
   <img width="1092" alt="Snipaste_2024-11-04_01-57-37" src="https://github.com/user-attachments/assets/30cf4f69-7a38-4265-8c7a-8fbf6dd65d9a">

7. 生成修补后的 Weixin.dll
   <img width="1092" alt="Snipaste_2024-11-04_01-59-40" src="https://github.com/user-attachments/assets/87a9275a-9b24-4fd9-ba7a-96bf1adae175">

完成了。非常感谢原教程提供的帮助。

如果喜欢的话可以来关注一下可爱的 zetaloop！

###### 这篇文章放在这儿只是为了水一个 repo 数 :)
