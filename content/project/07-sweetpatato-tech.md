+++
title = "大番薯项目技术实现"
date = 2024-09-30
updated = 2024-09-30

+++

## 通义千问 API使用

：D

## GPT-SoVITS 使用

：D

## 鼠标键盘模拟的实现

：D

## python 库

[pyautogui](https://pypi.org/project/PyAutoGUI/)

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