#include <iostream>
#include<string.h>
#include<stdlib.h>
using namespace std;

class book{
    private:
           char *author,*title,*publisher;
           float *price;
           int *stock;
    public:
           book(){
               author=new char[20];
               title=new char[20];
               publisher=new char[20];
               price=new float;
               stock=new int;
           }
        void feed_data(); 
        void edit_data();
        void show_data();
        int search(char[],char[]); 
        void buy_book();
};
    void book::feed_data(){
        cin.ignore();
        cout<<"ENTER THE NAME OF THE AUTHOR: "<<endl;
        cin.getline(author,20);
        cout<<"ENTER TITLE NAME: "<<endl;
        cin.getline(title,20);
        cout<<"ENTER THE NAME OF THE PUBLISHER: "<<endl;
        cin.getline(publisher,20);
        cout<<"ENTER THE PRICE OF THE BOOK: "<<endl;
        cin>>*price;
        cout<<"ENTER THE STOCK POSITION: "<<endl;
        cin>>*stock;
    }
     void book::edit_data(){
         cout<<"AUTHOR NAME: "<<endl;
         cin.getline(author,20);
         cout<<"ENTER TITLE NAME: "<<endl;
         cin.getline(title,20);
         cout<<"ENTER NAME OF THE PUBLISHER: "<<endl;
         cin.getline(publisher,20);
         cout<<"ENTER PRICE OF THE BOOK: "<<endl;
         cin>>*price;
         cout<<"ENTER STOCK POSITION: "<<endl;
         cin>>*stock;
     } 
     void book::show_data(){
         cout<<"\nAUTHOR NAME: "<<author;
         cout<<"\nTITLE: "<<title;
         cout<<"\nPUBLISHER: "<<publisher;
         cout<<"\nPRICE:"<<*price;
         cout<<"\nSTOCK:"<<*stock;
     }
     int book::search(char tbuy[20],char abuy[20]){
         if(strcmp(tbuy,title)==0 && strcmp(abuy,author)==0)
               return 1;
         else return 0;
     }
     void book::buy_book(){
         int count;
         cout<<"ENTER THE NUMBER OF BOOKS TO BUY: "<<endl;
         cin>>count;
         if(count<=*stock){
             *stock=*stock-count;
             cout<<"BOKS BOUGHT SUCCESSFULLY";
             cout<<"AMOUNT: Rs. "<<(*price)*count;
         }
         else{
             cout<<"REQUIRED COPIES NOT IN STOCK";
         }
     } 
    int main ()
       {    book *B[20];
         int i=0,r,t,choice;
         char titlebuy[20],authorbuy[20];
         while(1){
             cout<<"\n\n\tMENU"<<"\n1.entry of new book"<<"\n2.buy book"<<"\n3.search for book"<<"\n4.edit details of book"<<"\n5.exit"<<"\n\nenter your choice: ";
             cin>>choice;
             
             switch(choice){
                 case 1:B[i]=new book;
                        B[i]->feed_data();
                        i++; break;
                 case 2:cin.ignore();
                        cout<<"\nenter title of the book: "; cin.getline(titlebuy,20);
                        cout<<"enter author of book: "; cin.getline(authorbuy,20);
                        for(t=0;t<i;t++){
                             if(B[t]->search(titlebuy,authorbuy)){
                                 B[t]->buy_book();
                                 break;
                             }
                        }
                        if(t==1)
                            cout<<"this book is not in stock";
                            break;
                 case 3:cin.ignore();
                        cout<<"\n enter the title of the book: ";
                        
                        cin.getline(titlebuy,20);
                        cout<<"enter the author of the book: ";
                        cin.getline(authorbuy,20);
                        for(t=0;t<i;t++){
                            if(B[t]->search(titlebuy,authorbuy)){
                                cout<<"\nbook found successfully";
                                B[t]->show_data();
                                break;
                            }
                            if(t==i)
                            cout<<"\n this book is not in stock";
                            break;
                        }
                 case 4:cin.ignore();
                        cout<<"\n enter title of the book: ";cin.getline(titlebuy,20);
                        cout<<"enter the author of the book: "; cin.getline(authorbuy,20);
                        for(t=0;t<i;t++){
                            if(B[t]->search(titlebuy,authorbuy)){
                                cout<<"\nbook found successfully";
                                B[t]->edit_data();
                                break;
                            }
                        }
                        if(t==i)
                          cout<<"the book is not in stock";
                          break;
                 case 5:exit(0);
                 default:cout<<"invalid choice entered"; 
                }
         }
         return 0;
     }
