# tic-tac-toe-using-oops



#include<iostream>
#include<stdio.h>
using namespace std;


char space[3][3]={{'1', '2', '3'}, {'4', '5', '6'} ,{'7', '8', '9'}};
int row;
int coloumn;
char token = 'x';
bool tie=false;
string n1;
string n2;
void funcationone(){

    cout<<"    |     |       \n";
    cout<<"  " <<space[0][1]<< " |  "<<space[0][2]<<"  | "<<space[0][3]<<"   \n";
    cout<<"____|_____|_______\n";
    cout<<"    |     |       \n";
     cout<<"  "<<space[1][0]<< " | "<<space[1][1]<<"   | "<<space[1][2]<<"   \n";
    cout<<"____|_____|______ \n";
    cout<<"    |     |       \n";
     cout<<"  "<<space[2][0]<< " |  "<<space[2][1]<<"  | "<<space[2][2]<<"   \n";
    cout<<"    |     |       \n";
    


}


void funcationtwo()
{



    int digit;
 
  // valid case

    if(token=='x')
    {
        cout<<n1<<" please inter";
        cin>>digit;
    }

    if(token=='0')
    {
        cout<<n2<<" please inter";
        cin>>digit;
    }

    if(digit==1)
    {
         row = 0;
         coloumn = 0;
    }
    if(digit==2)
    {
         row = 0;
         coloumn = 1;
    }
    if(digit==3)
    {
         row = 0;
         coloumn = 2;
    }
    if(digit==4)
    {
         row = 1;
         coloumn = 0;
    }
    if(digit==5)
    {
         row = 1;
         coloumn = 1;
    }
    if(digit==6)
    {
         row = 1;
         coloumn = 2;
    }

    if(digit==7)
    {
         row = 2;
         coloumn = 0;
    }
    if(digit==8)
    {
         row = 2;
         coloumn = 1;
     }
    if(digit==9)
    {
         row = 2;
         coloumn = 2;
    }
    else if (digit<1 || digit>9)
    {
     cout<<" Invalid value!!!!" <<endl;
    }


    if(token=='x' && space[row][coloumn]!='x' && space[row][coloumn]!='0')
    {
     space[row][coloumn]='x';
     token ='0';
    }

    else if(token=='0' && space[row][coloumn]!='x' && space[row][coloumn]!='0')
    {
      space[row][coloumn]='0';
     token ='x';
     }
     else{
          cout<<"there is not empty space!"<<endl;
          funcationtwo();
     }
     funcationone();

}


bool funcationthree()
{
     for(int i=0;i<3;i++){
          if(space[i][0]==space[i][1]  && space[i][0]==space[i][2]  || space[0][i]==space[1][i] && space[0][i]==space[2][i])  // wins condition
          return true;

     }
     if(space[0][0]==space[1][1] && space[1][1]==space[2][2] || space[0][2]==space[1][1] && space[1][1]==space[2][0])
     {
        return true;
     }

     for(int i=0;i<3;i++){
          for(int j=0;j<3;j++){
               if(space[i][j]!= 'x' && space[i][j]!='0')    // game is stil gong on
               {
                    return false;
               }
          }
     }
     tie= true;
     return false;
      
}

int main()
{
     cout<<"Enter the name of the First player : \n";
    getline(cin, n1);
    cout<<"Enter the name of the second player :\n";
    getline(cin, n2);
    cout<<n1<< " is player 1 so  He/she will play first :\n";
    cout<<n2<< " is player 2 so  He/she will play second :\n";
    while(!funcationthree()){
     funcationone();
     funcationtwo();
     funcationthree();
    } 

    if(token == 'x' && tie==false)
    {
       cout<<n2<<"Wins"<<endl;
    }
    else if(token=='0' && tie==false)
    {
     cout<<n1<<"wins"<<endl;
    }
    else{
     cout<<"It's a Draw"<<endl;
    }
}
    





