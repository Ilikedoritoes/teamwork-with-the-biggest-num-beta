#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>

#define N 9
void main()
{
    int num[N], index, i, temp,max;
    int middlenums = N / 3;
    printf("please enter %d numbers that can be devided by 3\n",N);

    //קליטת המספרים 
    for (index = 0; index < N; index++)
    {
        scanf("%d", &num[index]);
    }

    printf("\n");

     //שינוי ערך המספרים
    for (i = 0; i < middlenums; i++)
    {
        temp = num[i];
        num[i] = num[i + (2 * middlenums)];
        num[i + (2 * middlenums)] = temp;
    }
    
    // הדפסת המספרים מחדש
    for (i = 0; i < N; i++)
    {
        printf("%d", num[i]);
    }

    printf("\n");

    //מציאת מספר הכי גדול
    max = num[middlenums];
    for (i = middlenums; i < middlenums * 2;i++)
    {
        if (max < num[i])
            max = num[i];
    }

    printf("max number in the middle part is %d", max);
    system("pause");
}
