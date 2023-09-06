#include <stdio.h>
#include <stdlib.h>

int diagonalDifference(int arr_rows, int arr_columns, int** arr) {
    int primaryDiagonalSum = 0;
    int secondaryDiagonalSum = 0;

    for (int i = 0; i < arr_rows; i++) {
        primaryDiagonalSum += arr[i][i];
        secondaryDiagonalSum += arr[i][arr_columns - 1 - i];
    }

    return abs(primaryDiagonalSum - secondaryDiagonalSum);
}

int main() {
    int n;
    scanf("%d", &n);

    int** arr = (int**)malloc(n * sizeof(int*));
    for (int i = 0; i < n; i++) {
        arr[i] = (int*)malloc(n * sizeof(int));
        for (int j = 0; j < n; j++) {
            scanf("%d", &arr[i][j]);
        }
    }

    int result = diagonalDifference(n, n, arr);
    printf("%d\n", result);

    // Free memory
    for (int i = 0; i < n; i++) {
        free(arr[i]);
    }
    free(arr);

    return 0;
}