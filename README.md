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
    return 0;<BR><br>
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
