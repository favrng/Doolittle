#include <stdio.h>

int main(){
printf ("Doolittle\n");
//Masukkin matriks
float A[5][5], B[5], L[5][5], U[5][5], X[5], Y[5];
int n;
printf ("Masukkan dimensi persamaan linear:");
scanf ("\n%d", &n);
int i,j,k;
//Masukin matriks A
printf ("Masukkan koefisien persamaan secara berurutan:\n",n);
for (i=0; i<=n-1; i++){
    for (j=0; j<=n-1; j++){
        printf ("A[%d][%d]=", i, j);
        scanf ("%f", &A[i][j]);
    }
}
//Masukkin matriks B (hasil)
printf ("Masukkan ruas kanan persamaan secara berurutan:\n",n);
for (i=0; i<=n-1; i++){
        printf ("B[%d]=", i);
        scanf ("%f", &B[i]);
}

// print matriks a
printf ("\nMatriks A (koefisien persamaan):");
for (i=0; i<=n-1; i++){
        printf ("\n");
    for (j=0; j<=n-1; j++){
        printf ("%f\t", A[i][j]);
    }
}
// print matriks B
printf ("\nMatriks B (hasil persamaan):");
for (i=0; i<=n-1; i++){
        printf ("\n%f", B[i]);
    }
for (i=0; i<n; i++){
        for (j=0; j<n; j++){
                U[i][j] = 0;
                L[i][j]=0;
        }
}
// Memecah matriks A menjadi L dan U
float sum =0;
for (i=0; i<n; i++){
        for (j=0; j<n; j++){
            if (j>i)
            {
                L[i][j] = 0;
                for (k=0; k<=i-1; k++){
                sum = sum + (L[i][k]*U[k][j]);
                }
                U[i][j]=A[i][j]-sum;
                sum = 0;
            }
            else if (j==i){
                L[i][j]=1;
                for (k=0; k<=i-1; k++){
                sum = sum + (L[i][k]*U[k][j]);
                }
                U[i][j]=A[i][j]-sum;
                sum = 0;
                }
        else{
            U[i][j] = 0;
            for (k=0; k<=i-1; k++){
                sum = sum + (L[i][k]*U[k][j]);
                }
            L[i][j]= (A[i][j]-sum)/U[j][j];
            sum = 0;
                }
                }
}

//print matriks L dan U
printf ("\nMatriks A dipecah menjadi L*U.\nMatriks L:");
for (i=0; i<=n-1; i++){
        printf ("\n");
    for (j=0; j<=n-1; j++){
        printf ("%f\t", L[i][j]);
    }
}
printf ("\nMatriks U:");
for (i=0; i<=n-1; i++){
        printf ("\n");
    for (j=0; j<=n-1; j++){
        printf ("%f\t", U[i][j]);
    }
}

//Cari y pake forward substitution
Y[0] = B[0];
for (i=1; i<=n-1; i++){
    for (k=0; k<=i-1; k++){
        sum = sum + (L[i][k]*Y[k]);
    }
    Y[i]=B[i]-sum;
    sum = 0;
}
//Cari X pake backward substitution ^_^
X[n-1] = Y[n-1]/U[n-1][n-1];
for (i=n-2; i>=0; i--){
    for (k=i+1;k<=n-1;k++){
        sum = sum + (U[i][k]*X[k]);
    }
    X[i]=((Y[i]-sum)/U[i][i]);
    sum = 0;
}
// print matriks Y
printf ("\nMatriks menjadi LUX = B. Misalkan matriks UX=Y, sehinga LY = B. Matriks Y:");
for (i=0; i<=n-1; i++){
        printf ("\n%f", Y[i]);
    }
// print matriks X
printf ("\nSelesaikan UX = Y, untuk mendapat X sebagai solusi. Solusinya:");
for (i=0; i<=n-1; i++){
        printf ("\n x%d = %f", i+1, X[i]);
    }
return 0;
}
