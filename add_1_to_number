#include <bits/stdc++.h> 
using namespace std; 
 
struct Node
{
    int data;
    struct Node* next;
 
    Node(int x){
        data = x;
        next = NULL;
    }
};
 
void printList(Node* node) 
{ 
    while (node != NULL) { 
        cout << node->data; 
        node = node->next; 
    }  
    cout<<"\n";
} 
 
 
 // } Driver Code Ends
//User function template for C++
 
/* 
 
struct Node
{
    int data;
    struct Node* next;
    
    Node(int x){
        data = x;
        next = NULL;
    }
};
 
*/
 
class Solution
{
 
    private:
    Node* reverse (Node *&head)
    {
        Node *prev=NULL,*nxtptr,*curr=head;
        while(curr!=NULL)
        {
           nxtptr = curr->next;
           curr->next = prev;
           prev = curr;
           curr = nxtptr;
        }
       return prev;
    }
 
   public:
    int carry=0 ,sum=0;
   Node* addOne(Node *head) 
   {
      head =  reverse(head);
      head ->data +=1;
      Node *ptr=head,*prev;
      while(ptr!=NULL)
      {
           sum = ptr->data +carry ;
           ptr->data = sum %10;
            carry = sum/10;
            prev = ptr;
            ptr = ptr ->next;
      }
      if(carry)  prev->next = new Node(1);
       head = reverse(head);
       return head;
   }
};
 
// { Driver Code Starts.
 
int main() 
{ 
    int t;
    cin>>t;
    while(t--)
    {
        string s;
        cin>>s;
 
        Node* head = new Node( s[0]-'0' );
        Node* tail = head;
        for(int i=1; i<s.size(); i++)
        {
            tail->next = new Node( s[i]-'0' );
            tail = tail->next;
        }
        Solution ob;
        head = ob.addOne(head);
        printList(head); 
    }
    return 0; 
}
