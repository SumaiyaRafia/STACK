#include<iostream>
using namespace std;

#define stack_size 10
int top= -1;
char stack[stack_size];
char v;

void push(char);
char pop();
void display();


int main(){
    int choice;
    while(1){
        cout<<"\n0)Exit 1)Push 2)Pop 3)Display\nOption: ";
        cin>> choice;
        if(choice==0)return 0;
        else if(choice == 1){
            cout<<"Enter the elements"<<endl;
            cin>>v;
            push(v);

            //input element and call push function
        }
        else if(choice == 2){

            v=pop();
            //call pop here and assign the returned value to v
            //and show the popped value
            cout<<"The popped element is:"<< &v <<endl;

        }
        else if(choice == 3){
            //call display here to show all elements in the stack
            display();

        }
        else cout<<"Wrong option!\n\n";
    }
    return 0;
}


void push(char X){
    if(top >= stack_size -1)
        cout<<"Overflow! \n";
    else{
        top++;
        stack[top]=X;
        cout<<"Element pushed\n"<<X;
    }
}

char pop(){
    char X;
    if(top<0){
        cout<<"Underflow!\n";
        return '!';
    }

    else {
        X=stack[top];
        top--;
    }
    return X;
}

void display(){
    //define display to print all the elements in the stack
    if(top==-1)
    {
        cout<<"Stack is empty"<<endl;
    }
    else
    {
       int i ;
       cout<<"the stack elements :"<<endl;
       for(i=0;i<=top;i++)
       {
           cout<<stack[i];
       }
    }
}



