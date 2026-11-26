
#include <stdlib.h>

int** matrixReshape(int** mat, int matSize, int* matColSize,
                    int r, int c, int* returnSize,
                    int** returnColumnSizes) {

    int m = matSize;
    int n = matColSize[0];

    // Check if reshaping is possible
    if (m * n != r * c) {
        *returnSize = m;
        *returnColumnSizes = matColSize;
        return mat;
    }

    int** result = (int**)malloc(r * sizeof(int*));

    *returnSize = r;
    *returnColumnSizes = (int*)malloc(r * sizeof(int));

    for (int i = 0; i < r; i++) {
        result[i] = (int*)malloc(c * sizeof(int));
        (*returnColumnSizes)[i] = c;
    }

    // Copy elements in row-traversing order
    for (int i = 0; i < m * n; i++) {
        result[i / c][i % c] = mat[i / n][i % n];
    }

    return result;
}
