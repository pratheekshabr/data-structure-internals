# data-structure-internals
*****************************************************
1. Write a program to implement Breadth First Search for undirected graph (BFS).
*****************************************************
#include<iostream><BR>
#include<conio.h><br>
#include<stdlib.h><br>
using namespace std;<br>
 int cost[10][10],qu[10],front,rare,visit[10],visited[10];<br>
int main()<br>
{<br>

   int m,n,j,i,v,k;<br>
    cout <<"Enter no of vertices:";<br>
    cin >> n;<br>
    cout <<"Enter no of edges:";<br>
    cin >> m;<br>
    cout <<"\nEDGES \n";<br>
    for(k=1; k<=m; k++)<br>
    {<br>
        cin >>i>>j;<br>
        cost[i][j]=1;<br>
    }<br>
    cout <<"Enter initial vertex to traverse from:";<br>
    cin >>v;<br>
    cout <<"Visitied vertices:";<br>
    cout <<v<<" ";<br>
    visited[v]=1;<br>
    k=1;<br>
    while(k<n)<br>
    {<br>
        for(j=1; j<=n; j++)<br>
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
            {<br>
                visit[j]=1;<br>
                qu[rare++]=j;<br>
            }<br>
        v=qu[front++];<br>
        cout<<v <<" ";<br>
        k++;<br>
        visit[v]=0;<br>
        visited[v]=1;<br>
    }<br>
    return 0;<BR>
}<br>
  
 Output:
 ******
 
 ***************************************
  2. Write a program to implement Depth First Search for undirected graph (DFS).<BR><br>
 **************************************
#include<iostream><BR>
#include<conio.h><BR>
#include<stdlib.h><BR>
using namespace std;<BR>
int cost[10][10],i,j,k,n,stk[10],top,v,visit[10],visited[10];<BR>
int main()<BR>
{<BR>
    int m;<BR>
    cout <<"Enter no of vertices:";<BR>
    cin >> n;<BR>
    cout <<"Enter no of edges:";<BR>
    cin >> m;<BR>
    cout <<"\nEDGES \n";<BR>
    for(k=1; k<=m; k++)<BR>
    {<BR>
        cin >>i>>j;<BR>
        cost[i][j]=1;<BR>
    }<br>
    cout <<"Enter initial vertex to traverse from:";<br>
    cin >>v;<br>
    cout <<"DFS ORDER OF VISITED VERTICES:";<br>
    cout << v <<" ";<br>
    visited[v]=1;<br>
    k=1;<br>
    while(k<n)<br>
    {<br>
        for(j=n; j>=1; j--)<br>
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
            {<br>
                visit[j]=1;<br>
                stk[top]=j;<br>
                top++;<br>
            }<br>
        v=stk[--top];<br>
        cout<<v << " ";<br>
        k++;<br>
        visit[v]=0;<br>
        visited[v]=1;<br>
    }<br><br>
    return 0;<br>
}<br>
 
 ***********************
 3.Write a C++program to solving the N-Queen'sproblem using Backtracking.<br>
 ***********************
#define N 4<br>
#include <stdbool.h><br>
#include <stdio.h><br>
void printSolution(int board[N][N])<br>
{<br>
for (int i = 0; i < N; i++) {<br>
for (int j = 0; j < N; j++)<br>
printf(" %d ", board[i][j]);<br>
printf("\n");<br>
}<br>
}<br>
bool isSafe(int board[N][N], int row, int col)<br>
{<br>
int i, j;<br><br>
for (i = 0; i < col; i++)<br>
if (board[row][i])<br>
return false;<br>
for (i = row, j = col; i >= 0 && j >= 0; i--, j--)<br>
if (board[i][j])<br>
return false;<br>
for (i = row, j = col; j >= 0 && i < N; i++, j--)<br>
if (board[i][j])<br>
return false;<br>
return true;<br>
}<br>
bool solveNQUtil(int board[N][N], int col)<br>
{<br>
if (col >= N)<br>
return true;<br>
for (int i = 0; i < N; i++) {<br>
if (isSafe(board, i, col)) {<br>
board[i][col] = 1;<br>
if (solveNQUtil(board, col + 1))<br>
return true;<br>
board[i][col] = 0; }<br>
}<br>
return false;<br>
}<br>
bool solveNQ()<br>
{<br>
int board[N][N]; <br>
for(int i=0;i<N;i++){<br>
for(int j=0;j<N;j++){<br>
board[i][j] = 0;<br>
}<br>
}<br>
if (solveNQUtil(board, 0) == false) {<br>
printf("Solution does not exist");<br>
return false;<br>
}<br>
printSolution(board);<br>
return true;<br>
}<br>
int main()<br>
{<br>
solveNQ();<br>
return 0;<br>
}<br>
