### [QUESTÃO – 05]
### Implemente uma solução para multiplicação de matrizes utilizando programação dinâmica, visando determinar uma ordem em que as matrizes sejam multiplicadas, de modo a minimizar o número de multiplicações envolvidas.  
    // See the Cormen book for details of the following algorithm
    // Código retirado do site https://www.geeksforgeeks.org/c-program-for-matrix-chain-multiplication-dp-8/.
    #include <limits.h> 
    #include <stdio.h> 

    // Matrix Ai has dimension p[i-1] x p[i] for i = 1..n 
    int MatrixChainOrder(int p[], int n) 
    { 

        /* For simplicity of the program, one extra row and one 
           extra column are allocated in m[][].  0th row and 0th 
           column of m[][] are not used */
        int m[n][n]; 

        int i, j, k, L, q; 

        /* m[i, j] = Minimum number of scalar multiplications needed 
           to compute the matrix A[i]A[i+1]...A[j] = A[i..j] where 
           dimension of A[i] is p[i-1] x p[i] */

        // cost is zero when multiplying one matrix. 
        for (i = 1; i < n; i++) 
            m[i][i] = 0; 

        // L is chain length. 
        for (L = 2; L < n; L++) { 
            for (i = 1; i < n - L + 1; i++) { 
                j = i + L - 1; 
                m[i][j] = INT_MAX; 
                for (k = i; k <= j - 1; k++) { 
                    // q = cost/scalar multiplications 
                    q = m[i][k] + m[k + 1][j] + p[i - 1] * p[k] * p[j]; 
                    if (q < m[i][j]) 
                        m[i][j] = q; 
                } 
            } 
        } 

        return m[1][n - 1]; 
    } 

    int main() 
    { 
        int arr[] = { 40, 20, 30, 10, 30 }; 
        int size = sizeof(arr) / sizeof(arr[0]); 

        printf("Minimum number of multiplications is %d ", 
               MatrixChainOrder(arr, size)); 

        getchar(); 
        return 0; 
    } 

O código foi testado no site https://www.jdoodle.com/c-online-compiler com as entradas [ 40, 20, 30, 10, 30 ] e como saída o número mínimo de multiplicações sendo ele 26000.
