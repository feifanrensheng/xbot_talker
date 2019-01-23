# Xbot语音对话程序

compile:
```bash
catkin_make --pkg xbot_talker
```

rosrun:
```bash
rosrun xbot_talker talker
```

roslaunch:
```bash
roslaunch xbot_talker talker.launch
```
包含两个服务:请求对话，请求播放
/request_talker
/request_play

---
/request_talker
request_talker.srv

int32 request_talker
---
string response

usage:启动请求对话
bash
rosservice call /request_talker "request_talker: 1" 
语音识别 "关闭" 可以终止对话，等待下一次对话请求。

usage:启动请求播放
bash
rosservice call /request_play "choose: 0
path: ''
text: ''"
---
choose: 1播放离线生成的wav语音文件; 2在线文字转语音播放
path: 'wav文件的绝对路径'
text: '想要播放的中文句子'

