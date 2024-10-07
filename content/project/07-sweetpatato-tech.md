+++
title = "大番薯项目技术实现"
date = 2024-09-30
updated = 2024-10-07

+++

## 通义千问 API使用

：D

## GPT-SoVITS 使用

：D

## 鼠标键盘模拟的实现

：D

## python 库

[PyAutoGui](https://pypi.org/project/PyAutoGUI/)

[PyAutoGui 中文文档](https://github.com/asweigart/pyautogui/blob/master/docs/simplified-chinese.ipynb)内已经有非常详尽的使用说明了，只要确定使用流程即可。

```
# 点击参数
pyautogui.click(x=moveToX, y=moveToY, clicks=num_of_clicks, interval=secs_between_clicks, button='left')

# 打印所有键盘参数
# print(pyautogui.KEYBOARD_KEYS)

# 查看屏幕大小
# pyautogui.position()
# screenWidth, screenHeight = pyautogui.size()
# print("width: ", screenWidth, "height: ", screenHeight)

# 查看鼠标位置
# print('Press Ctrl-C to quit')
# try:
#     while True:
#         x, y = pyautogui.position()
#         positionStr = 'X: {} Y: {}'.format(*[str(x).rjust(4) for x in [x, y]])
#         print(positionStr, end='')
#         print('\b' * len(positionStr), end='', flush=True)
# except KeyboardInterrupt:
#     print('\n')

# print(pyautogui.KEYBOARD_KEYS)

# 操作鼠标进行聊天
import pyautogui

pyautogui.moveTo(3146, 2098, duration=2)
pyautogui.leftClick()
pyautogui.moveTo(3052, 1843, duration=2)
pyautogui.leftClick()
for i in range(10):
    print("第", i+1, "次开始")
    pyautogui.moveTo(142, 1158, duration=2)#阿皮
    pyautogui.doubleClick()
    pyautogui.moveTo(1661, 1169, duration=1)#右击聊天框
    pyautogui.leftClick()
    # pyautogui.moveTo(1808, 1345, duration=2)#点击粘贴
    # pyautogui.leftClick()
    pyautogui.hotkey('ctrl', 'v')#通过键盘粘贴
    pyautogui.typewrite('Hello ', interval=0.25)
    if i == 5:
        pyautogui.press('num5')
    elif i == 6:
        pyautogui.press('num6')
    elif i == 7:
        pyautogui.press('num7')
    pyautogui.typewrite(' world!', interval=0.25)
    pyautogui.moveTo(2479, 1753, duration=1)#点击发送
    pyautogui.leftClick()
    pyautogui.moveTo(2618, 252, duration=2)#点击关闭
    pyautogui.leftClick()
    pyautogui.moveTo(124, 1309, duration=2)#杂良丸
    pyautogui.doubleClick()
    pyautogui.moveTo(1661, 1169, duration=1)#右击聊天框
    pyautogui.leftClick()
    # pyautogui.moveTo(1808, 1345, duration=2)#点击粘贴
    # pyautogui.leftClick()
    pyautogui.hotkey('ctrl', 'v')#通过键盘粘贴
    pyautogui.typewrite('Hello ', interval=0.25)
    if i == 5:
        pyautogui.press('num5')
    elif i == 6:
        pyautogui.press('num6')
    elif i == 7:
        pyautogui.press('num7')
    pyautogui.typewrite(' world!', interval=0.25)
    pyautogui.moveTo(2479, 1753, duration=1)#点击发送
    pyautogui.leftClick()
    pyautogui.moveTo(2618, 252, duration=2)#点击关闭
    pyautogui.leftClick()
    print("第", i+1, "次结束")

```

button7location = pyautogui.locateOnScreen('1.png')

图片定位的功能不太好用

[排错](https://blog.csdn.net/m0_53911267/article/details/134731286#:~:text=PyAuto)

查看 pip 安装包的版本

pip list | findstr PyScreeze

[source](https://blog.csdn.net/PSpiritV/article/details/123244634#:~:text=%E4%B8%80%E3%80%81%E5%A6%82%E4%BD%95%E6%9F%A5%E7%9C%8B)

安装指定版本的包

pip install package==version

[source](https://blog.csdn.net/weixin_43289135/article/details/120097579)

## Windows API

参考视频试了一下 windows API 的基本使用，模拟键盘基本没什么问题，应该基本上每个鼠标点击和键盘输入都有相应的函数去实现。

相关函数及对应功能：

```
// 获取窗口句柄
HWND wcHwnd;
wcHwnd = FindWindow("TXGuiFoundation", "158790750");
// 将窗口设置为前台窗口
SetForegroundWindow(wcHwnd);
// 获取当前前台窗口句柄
apiHwnd == GetForegroundWindow()
// 发送消息到窗口
SendMessage(qqhwnd, WM_PASTE, 0, 0);//粘贴消息
SendMessage(qqhwnd, WM_KEYDOWN, VK_RETURN, 0);//点击回车
// 模拟键盘输入
keybd_event(VK_RETURN, 0, 0, 0);//点击
// 模拟鼠标移动(鼠标还没试，键盘试过都ok)
SetCursorPos(x, y);
// 模拟鼠标点击
mouse_event(MOUSEEVENTF_LEFTDOWN, 0, 0, 0, 0);
mouse_event(MOUSEEVENTF_LEFTUP, 0, 0, 0, 0);
```

实现一个简单的模拟键盘输入的功能，具体流程是给 QQ 一个分组里的两个好友来回发送信息。
完整代码如下：

```
#include <iostream>
#include <stdio.h>
#include <windows.h>

void PressOneKey(BYTE vkey) {
	keybd_event(vkey, 0, 0, 0);
	Sleep(50);
	keybd_event(vkey, 0, 2, 0);
	Sleep(50);
}

void PressTwoKey(BYTE vkey1, BYTE vkey2) {
	keybd_event(vkey1, 0, 0, 0);
	Sleep(50);
	keybd_event(vkey2, 0, 0, 0);
	Sleep(50);
	keybd_event(vkey2, 0, 2, 0);
	Sleep(50);
	keybd_event(vkey1, 0, 2, 0);
	Sleep(50);
}

int main() {
    HWND qqHwnd;
    HWND apiHwnd;
    HWND zlwHwnd;
    HWND wcHwnd;


    qqHwnd = FindWindow("TXGuiFoundation", "QQ");
    wcHwnd = FindWindow("TXGuiFoundation", "1587907XX");
    printf("程序开始\n");
    int i = 1;
    for (i == 1; i < 10; i++)
    {
        printf("第 %d 轮开始\n", i);
        SetForegroundWindow(wcHwnd);
        Sleep(1000);
        SetForegroundWindow(qqHwnd);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_RETURN);
        Sleep(1000);
        apiHwnd = FindWindow("TXGuiFoundation", "阿皮等2个会话");
        if (apiHwnd == GetForegroundWindow()) {
            PressTwoKey(VK_CONTROL, 'V');
            Sleep(1000);
            PressOneKey(VK_RETURN);
            Sleep(1000);
            PressOneKey(VK_ESCAPE);
            Sleep(1000);
            printf("给阿皮发送完成\n");
        }
        else {
            printf("开错聊天框了\n");
        }
        Sleep(5000);
        SetForegroundWindow(wcHwnd);
        Sleep(1000);
        SetForegroundWindow(qqHwnd);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_DOWN);
        Sleep(1000);
        PressOneKey(VK_RETURN);
        Sleep(1000);
        zlwHwnd = FindWindow("TXGuiFoundation", "杂良丸等2个会话");
        if (zlwHwnd == GetForegroundWindow()) {
            PressTwoKey(VK_CONTROL, 'V');
            Sleep(1000);
            PressOneKey(VK_RETURN);
            Sleep(1000);
            PressOneKey(VK_ESCAPE);
            Sleep(1000);
            printf("给杂良丸发送完成\n");
        }
        else {
            printf("开错聊天框了\n");
        }
        SetForegroundWindow(wcHwnd);
        Sleep(1000);
        SetForegroundWindow(qqHwnd);
        PressOneKey(VK_TAB);		
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_TAB);
        Sleep(1000);
        PressOneKey(VK_UP);
        printf("第 %d 轮结束\n", i);
        Sleep(5000);
    }
}
```

更多函数应该可以参考这个：[windows系统的基础操作接口](https://learn.microsoft.com/en-us/windows/win32/)

参考链接：

[windows系统的基础操作接口](https://learn.microsoft.com/en-us/windows/win32/)

[键盘模拟器1](https://www.bilibili.com/video/BV18h411z7AF/?spm_id_from=333.999.0.0)

[键盘模拟器2](https://www.bilibili.com/video/BV1R64y1x7AW/?vd_source=174b189b0a6353093f9f16b62575a061)

[键盘模拟器3](https://www.bilibili.com/video/BV1Pb4y1r7Sj/?spm_id_from=333.999.0.0&vd_source=174b189b0a6353093f9f16b62575a061)

[Windows API是什么](https://zhuanlan.zhihu.com/p/141431725)

[一个键盘鼠标模拟参考](https://github.com/yangzhenping/KeyboardMouseSimulator/tree/master)

[鼠标模拟功能参考](https://www.bilibili.com/video/BV1qm4y1s7Ex/?spm_id_from=333.788.top_right_bar_window_history.content.click)

## 