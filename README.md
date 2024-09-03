# estrutura-de-dados

#include <stdio.h>

int main() {
    int arr[6], i, j, temp;
    
    for(i = 0; i < 6; i++)
        scanf("%d", &arr[i]);

    for(i = 0; i < 5; i++)
        for(j = 0; j < 5-i; j++)
            if(arr[j] > arr[j+1]) {
                temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }

    for(i = 0; i < 6; i++)
        printf("%d ", arr[i]);

    return 0;
}




2. 

#include <stdio.h>

int main() {
    int arr[6], i, j, min, temp;

    for(i = 0; i < 6; i++)
        scanf("%d", &arr[i]);

    for(i = 0; i < 5; i++) {
        min = i;
        for(j = i+1; j < 6; j++)
            if(arr[j] < arr[min])
                min = j;
        temp = arr[min];
        arr[min] = arr[i];
        arr[i] = temp;
    }

    for(i = 0; i < 6; i++)
        printf("%d ", arr[i]);

    return 0;
}




3.

#include <stdio.h>

void insertionSort(int arr[], int n) {
    int i, j, key;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[6], i;

    for(i = 0; i < 6; i++)
        scanf("%d", &arr[i]);

    insertionSort(arr, 6);

    for(i = 0; i < 6; i++)
        printf("%d ", arr[i]);

    return 0;
}
