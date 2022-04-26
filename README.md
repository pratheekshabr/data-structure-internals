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
 
Output:<br>
******<br>
 ![Screenshot (208)](https://user-images.githubusercontent.com/97940277/165235533-e62993fe-3e9d-4c94-9e50-eeab40cab7c4.png)<br>

 ****************************************
 4.Write a program to merge sort using divide and conquer method.<br>
 ******************************************************
 #include<iostream.h><br>
#include<conio.h><br>
void Merge(int*a,int low,int high,int mid)<br>
{<br>
	int i,j,k,temp[high-low+1]<br>
	i=low;<br>
	k=0;<br>
	j=mid+1;<br>
	while(i<=mid&&j<=high)<br>
	{<br>
		if(a[i]<a[j])<br>
		{<br>
			temp[k]=a[i];<br>
			k++;<br>
			i++;<br>
		}<br>
		else<br>
		{<br>
			temp[k]=a[j];<br>
			k++;<br>
			j++;<br>
		}<br>
	}<br>
	while(i<=mid)<br><br>
	{<br>
	temp[k]=a[i];<br>
	k++;<br>
	i++;<br>
	}<br>
 while(j<=high)<br>
		{<br>
	
temp[k]=a[j];<br>
k++;<br>
j++;<br>
}<br>
		

for(i=low;i<=high;i++)<br>
{<br>
a[i]=temp[i-low];<br>
}<br>
}<br>
void MergeSort(int*a,int low,int high)<br>
{<br>
int mid;<br>
if(low<high)<br>
{<br>
mid=(low+high)/2;<br>
MergeSort(a,low,mid);<br>
MergeSort(a,mid+1,high;<br>
Merge(a,low,high,mid);<br>
}<br>
}<br>
		
void Main()<br>
{<br>
int n,i;<br>
cout<<"\nEnter the number of data elements to be sorted:";<br>
cin>>n;<br>
int arr[n];<br>
for(i=0;i<n;i++)<br>
{<br>
cout<<"Enter element"<<i+1<<":";<br>
cin>>arr[i];<br>
}<br>
MergeSort(arr,0,n-1);<br>
cout<<"\nSorted Data";<br>
for(i=o;i<n;i++)<br>
cout<<"->"<<arr[i];<br>
getch();<br>
}<br>
			
			
Output:<br>
******<br>
![Screenshot (211)](https://user-images.githubusercontent.com/97940277/165237421-2e50cd07-0721-432b-9089-11ce2f4cd014.png)<br>
	
	
*********************************
5. write a C++Program to implement doubly linked list<br>
**************************************
#include<iostream><br>
#include<cstdio><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
    int info;<br>
    struct node *next;<br>
    struct node *prev;<br><br>
}*start;<br>
class double_llist<br>
{<br>
    public:<br>
        void create_list(int value);<br>
        void add_begin(int value);<br>
        void add_after(int value, int position);<br>
        void delete_element(int value);<br>
        void search_element(int value);<br>
        void display_dlist();<br>
        void count();<br>
        void reverse();<br>
        double_llist()<br>
        {<br>
            start = NULL; <br> 
        }<br>
};<br>
 int main()<br>
{<br>
    int choice, element, position;<br>
    double_llist dl;<br>
    while (1)<br>
    {<br>
        cout<<endl<<"----------------------------"<<endl;<br>
        cout<<endl<<"Operations on Doubly linked list"<<endl;<br>
        cout<<endl<<"----------------------------"<<endl;     <br>   
        cout<<"1.Create Node"<<endl;<br>
        cout<<"2.Add at begining"<<endl;<br>
        cout<<"3.Add after position"<<endl;<br>
        cout<<"4.Delete"<<endl;<br>
        cout<<"5.Display"<<endl;<br>
        cout<<"6.Count"<<endl;<br>
        cout<<"7.Reverse"<<endl;<br>
        cout<<"8.Quit"<<endl;<br>
        cout<<"Enter your choice : ";<br>
        cin>>choice;<br>
        switch ( choice )<br>
        {<br>
        case 1:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.create_list(element);<br>
            cout<<endl;<br>
            break;<br>
        case 2:<br><br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.add_begin(element);<br>
            cout<<endl;<br>
            break;<br>
        case 3:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            cout<<"Insert Element after postion: ";<br>
            cin>>position;<br>
            dl.add_after(element, position);<br>
            cout<<endl;<br>
            break;<br>
        case 4:<br>
            if (start == NULL)<br>
            { <br> <br>      
                cout<<"List empty,nothing to delete"<<endl;  <br>
                break;<br>
            }<br>
            cout<<"Enter the element for deletion: ";<br>
            cin>>element;<br>
            dl.delete_element(element);<br>
            cout<<endl;<br>
            break;<br>
        case 5:<br>
            dl.display_dlist();<br>
            cout<<endl;<br>
            break;<br>
        case 6:<br>
            dl.count();<br>
            break;    <br>
        case 7:<br>
            if (start == NULL)<br>
            {<br>
                cout<<"List empty,nothing to reverse"<<endl;<br>
                break;<br>
            }<br>
            dl.reverse();<br>
            cout<<endl;<br>
            break;<br><br>
        case 8:<br>
            exit(1);<br>
        default:<br>
            cout<<"Wrong choice"<<endl;<br>
        }<br>
    }<br>
    return 0;<br>
}<br>
 void double_llist::create_list(int value)<br>
{<br>
    struct node *s, *temp;<br>
    temp = new(struct node);<br>
    temp->info = value;<br>
    temp->next = NULL;<br>
    if (start == NULL)<br>
    {<br>
        temp->prev = NULL;<br>
        start = temp;<br>
    }<br>
    else<br>
    {<br>
        s = start;<br>
        while (s->next != NULL)<br><br>
            s = s->next;<br>
        s->next = temp;<br>
        temp->prev = s;<br>
    }<br>
}<br>
 void double_llist::add_begin(int value)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *temp;<br>
    temp = new(struct node);<br>
    temp->prev = NULL;<br>
    temp->info = value;<br>
    temp->next = start;<br>
    start->prev = temp;<br>
    start = temp;<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
void double_llist::add_after(int value, int pos)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *tmp, *q;<br>
    int i;<br>
    q = start;<br>
    for (i = 0;i < pos - 1;i++)<br>
    {<br>
        q = q->next;<br><br>
        if (q == NULL)<br>
        {<br>
            cout<<"There are less than ";<br>
            cout<<pos<<" elements."<<endl;<br>
            return;<br>
        }<br>
    }<br>
    tmp = new(struct node);<br>
    tmp->info = value;<br>
    if (q->next == NULL)<br>
    {<br>
        q->next = tmp;<br>
        tmp->next = NULL;<br>
        tmp->prev = q;      <br>
    }<br>
    else<br>
    {<br>
        tmp->next = q->next;<br>
        tmp->next->prev = tmp;<br>
        q->next = tmp;<br>
        tmp->prev = q;<br>
    }<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
 void double_llist::delete_element(int value)<br>
{<br>
    struct node *tmp, *q;<br>
        if (start->info == value)<br>
    {<br>
        tmp = start;<br>
        start = start->next;  
        start->prev = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        free(tmp);<br>
        return;<br>
    }<br>
    q = start;<br>
    while (q->next->next != NULL)<br>
    {  <br>
               if (q->next->info == value)  <br>
        {<br>
            tmp = q->next;<br>
            q->next = tmp->next;<br>
            tmp->next->prev = q;<br>
            cout<<"Element Deleted"<<endl;<br>
            free(tmp);<br>
            return;<br>
        }<br>
        q = q->next;<br>
    }<br>
        if (q->next->info == value)   <br> 
    {<br>
        tmp = q->next;<br>
        free(tmp);<br><br>
        q->next = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        return;<br>
    }<br>
    cout<<"Element "<<value<<" not found"<<endl;<br>
}<br>
 void double_llist::display_dlist()<br>
{<br>
    struct node *q;<br>
    if (start == NULL)<br>
    {<br>
        cout<<"List empty,nothing to display"<<endl;<br>
        return;<br>
    }<br>
    q = start;<br>
    cout<<"The Doubly Link List is :"<<endl;<br>
    while (q != NULL)<br>
    {<br><br>
        cout<<q->info<<" <-> ";<br>
        q = q->next;<br>
    }<br>
    cout<<"NULL"<<endl;<br>
}<br>
 void double_llist::count()<br>
{<br>
    struct node *q = start;<br>
    int cnt = 0;<br>
    while (q != NULL)<br>
    {<br>
        q = q->next;<br>
        cnt++;<br>
    }<br>
    cout<<"Number of elements are: "<<cnt<<endl;
}<br>
 void double_llist::reverse()<br>
{<br>
    struct node *p1, *p2;<br>
    p1 = start;<br>
    p2 = p1->next;<br>
    p1->next = NULL;<br>
    p1->prev = p2;<br>
    while (p2 != NULL)<br>
    {<br>
        p2->prev = p2->next;<br>
        p2->next = p1;<br>
        p1 = p2;<br>
        p2 = p2->prev;<br>
    }<br>
    start = p1;<br>
    cout<<"List Reversed"<<endl;<br>
}<br>
		
Output:<br>
******<br>
![Screenshot (160)](https://user-images.githubusercontent.com/97940277/163759755-d480a09a-6349-4aa1-9a7e-88dcffa0b61a.png)<br>
![Screenshot (161)](https://user-images.githubusercontent.com/97940277/163759850-0e2bc72a-8bc7-499a-8e3e-c40872911f17.png)<br>
![Screenshot (162)](https://user-images.githubusercontent.com/97940277/163759985-d8292c39-af25-4e8d-9b78-811cdd0be704.png)<br>
![Screenshot (163)](https://user-images.githubusercontent.com/97940277/163760147-17cbb7ea-0b46-454c-be91-07948b092695.png)<br>
![Screenshot (164)](https://user-images.githubusercontent.com/97940277/163760339-47f0b9b5-a149-4176-ac24-a2708e2b272b.png)<br>

	
