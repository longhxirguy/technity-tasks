#include <stdio.h>

int birthdayCakeCandles(int n, int candles[]) {
    int max_height = 0;
    int count = 0;

    // Find the maximum height of candles
    for (int i = 0; i < n; i++) {
        if (candles[i] > max_height) {
            max_height = candles[i];
            count = 1;
        } else if (candles[i] == max_height) {
            count++;
        }
    }

    return count;
}

int main() {
    int n;
    scanf("%d", &n);

    int candles[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &candles[i]);
    }

    int result = birthdayCakeCandles(n, candles);
    printf("%d\n", result);

    return 0;
}
