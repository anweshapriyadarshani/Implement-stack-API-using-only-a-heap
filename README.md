# Implement-stack-API-using-only-a-heap
Implement a stack API using only a heap. A stack implements the following methods:      push(item), which adds an element to the stack     pop(), which removes and returns the most recently added element (or throws an error if there is nothing on the stack)  Recall that a heap has the following operations:      push(item), which adds a new key to the heap     pop(), which removes and returns the max value of the heap

#include<bits/stdc++.h>
using namespace std;
typedef pair<int,int>pi;
class stack
{
	//cnt is used to keep track of numbers of elements in stack and serves as a priority queue
	int cnt;
	priorityqueue<pair<int,int>>pq;
	public:
	       stack(),cnt(0){}
		   void push(int n);
		   void pop();
		   int top();
		   bool isempty();
};
//push function increases cnt by 1 and inserts cnt with original value
void stack::push(int n)
{
	cnt++;
	 pq.push(pi(cnt, n)); 
} 
//pops element and reduces count
void stack::pop()
{
	if(pq.empty())
	{
		cout<<"nothing can pop";
	}
	cnt--;
	pq.pop();
}
//returns the top element in the stack using cnt as key to determine top(highest priority), default comparator for pairs works fine in this case  
		int stack::top()
		{
			pi temp=pq.top(); 
    return temp.second; 
} 
  
// return true if stack is empty 
bool Stack::isEmpty(){ 
    return pq.empty(); 
} 
  
// Driver code 
int main() 
{ 
    Stack* s=new Stack(); 
    s->push(1); 
    s->push(2); 
    s->push(3); 
    while(!s->isEmpty()){ 
        cout<<s->top()<<endl; 
        s->pop(); 
    } 
} 
		   

