#include <stdio.h>
#include <string.h>
#define NUM_BOOK 5

typedef struct{
    
char title[100];
char author[50];
int year;
float price;

}book;

void print_book( book b){
    printf("\ntitle= %s",b.title);
    printf("\nauthor= %s",b.author);
    printf("\nyear= %d",b.year);
    printf("\n price= %.1f",b.price);
    
}

int find_book_by_title(book books[], int size, char* title){
   for(int i=0;i<size;i++){
        if(strcmp(books[i].title,title)==0){
           return i;
        }
   }
    return -1;
}
void update_price( book* b, float new_price){
   b->price=new_price;
}

void print_all_books(book books[], int size){
    for(int i=0;i<size;i++){
         print_book(books[i]);
    }
}

void sort_books_by_year( book books[], int size){
    for(int i=0;i<size;i++){
        for(int j=0;j<size-(i+1);j++){
        if(books[j].year>books[j+1].year){
            book temp;
            temp=books[j];
            books[j]=books[j+1];
            books[j+1]=temp;
        }
        }
    }
    
}

int main(){
    
    book b[NUM_BOOK]={
        {"math","jake",1988,23.6},
        {"physics","leonard",1955,34.8},
        {"programming","anthony",1950,70.4},
        {"spanish","sammie",1934,50.6},
        {"python","berad",1999,60.2},
    };
        print_book(b[0]);
         
         
     int result=find_book_by_title(b,NUM_BOOK,"physics");
     printf(" \n \n %d ",result);
     
     
      update_price(&b[0],30);
      
      

      
      sort_books_by_year(b,NUM_BOOK);
      
       print_all_books(b,NUM_BOOK);
     
    

        
    }
    
    
v
