## 控制台处理
### stdlib.h
1. puts(const char *str);在当前光标处输出字符串str，光标自动右移
2. getch(); 从键盘获取一个字符,通常和kbhit()配合使用

### conio.h 
1. kbhit(); 判断是否有按键按下
```c
    #include <conio.h>
    system("cls");
    _cputs("please press a key\n");
    while (1)
    {
        _sleep(100);
        if(kbhit()){
            puts("get a ch:");
            c = getch();
            printf("%d\n",c);
        }
    }
```
### windows.h
1. SetConsoleCursorPosition(); 设置光标位置
```c
    #include <windows.h>
    system("cls");
    COORD pos={.X = 0, .Y = 0};
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), pos);
    printf("set cursor postioin @ 0,0");
    pos.X = 10; pos.Y = 10;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), pos);
    printf("set cursor postioin @ 10,10");
    printf("\r\n");
```
