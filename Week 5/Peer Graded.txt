/*

C Compiler

Average weight of elephant seals

26 Jun 2020

*/

#include <stdio.h>

#include <stdlib.h>

#include <malloc.h>

double average(int row,int column,int mat[row][column])

{

    int a;

    int b;

    double sum=0.0;

    for(a=0;a<row;a++)

        for(b=0;b<column;b++)

            sum+=mat[a][b];

    return(sum/1000);

}

int main()

{

    int i;

    int j;

    int r=50;

    int col=20;

    int** mat=malloc(r*sizeof(int*));
 
   for(i=0;i<r;++i)

    mat[i]=malloc(r*sizeof(int));

    FILE *file;

    file=fopen("data.txt", "r");/*Text file consisting of raw data in 50 rows and 20 columns*/

    for(i = 0; i < 1000; i++)

    {

        for(j = 0; j <col; j++)
 
       {

            if (!fscanf(file, "%d", &mat[i][j]))
 
           break;

            printf("%d\t",mat[i][j]);
 
           if(j==col-1)

            {

                printf("\n\n");

            }

            printf("Average of elephant seal is %.2f\n\n",average(r,col,mat));

        }

    }

    fclose(file);

    return 0;

}