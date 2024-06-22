+++
title = 'printf("Hello World");'
description = 'Hello world!'
date = 2023-04-27T13:45:50+02:00
draft = false
tags = ['hello world']
+++

```c
#include <stdio.h>

void main(){
    char hi[12];
    int i=0;
    while(i<12){
        switch (i){
            case 0:
                hi[i]='h';
                i++;
                break;
            case 1:
                hi[i]='e';
                i++;
                break;
            case 2:
                hi[i]='l';
                i++;
                break;
            case 3:
                hi[i]='l';
                i++;
                break;
            case 4:
                hi[i]='o';
                i++;
                break;
            case 5:
                hi[i]=' ';
                i++;
                break;
            case 6:
                hi[i]='w';
                i++;
                break;
            case 7:
                hi[i]='o';
                i++;
                break;
            case 8:
                hi[i]='r';
                i++;
                break;
            case 9:
                hi[i]='l';
                i++;
                break;
            case 10:
                hi[i]='d';
                i++;
                break;
            case 11:
                hi[i]='\0';
                i++;
                break;
    	}
    }
    printf("%s", hi);
}
```
