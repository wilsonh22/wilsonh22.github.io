---
layout: project
type: project
image: img/bank.jpg
title: "Bank Teller"
date: 2023-10-29
published: true
labels:
  - C
  - C++
summary: "A Bank Teller program that I developed for ICS 212."
---
This project is a CRUD app developed in C++ in ICS 212 class. CRUD stands for Create, Read, Update, Delete. The UI of this program cosisted of Add (add account), PrintAll(print all ,Find(find account), Delete( delete an account), and Quit(quit the program). Working on this program we learn to manpulate data through pointers to pass the records (bank accounts) we create and the use of IO functions like read and write to add to a file where the data can be saved. For this project to function you must be proficient in IO functions, Pointers (and double pointers), Loops, and using mustiple files that include each  other. 

In this project I was the sole coder for the whole coding project. This was the project for our ICS 212 class, everyone was expected to create the same bank teller program on their own based on the concepts we go over in class and the information given on the assignment page. Being the only person responsible for my code I had to account everything every error. function, and test case I had to make sure everything worked.

This coding project was the most difficult project I have worked on to this day and It is also the project that I have learned the most from. Through this journey I have learn how to problem solve my code and understand what I am trying to achieve in the code before coding it. I learned to use techniques like drawing out the code, write pseudocode, and writing possible test cases to account for errors.

Here is a snippet of a function that uses double pointers:
```cpp
int addRecord(struct record **start,int uaccountno, char uname[], char uaddress[] )
{
    int stop;
    stop = 0;
    if(debugmode == 1)
    {
         printf("\nDebug Mode: addRecord");
         printf("\naccountNum: %d\n", uaccountno);
         printf("name: %s\n", uname);
         printf("address: %s\n", uaddress);
    }
    if(*start == NULL)
    {
       struct record* ptr = (struct record*)malloc(sizeof(struct record));
       if(ptr == NULL)
       {
           stop = -1;
           return stop;
       }
        (*start) = ptr;
        ptr->accountno = uaccountno;
        strncpy(ptr->name,uname,sizeof(ptr->name)-1);
        strncpy(ptr->address,uaddress,sizeof(ptr->address)-1);
        ptr->next = NULL;
    }
    else
    {
        struct record* temp;
        struct record* previous;
        temp = *start;
        previous = NULL;
        while(temp != NULL)
        {
            if(uaccountno == temp->accountno)
            {
            stop = -1;
            temp = NULL;
            return stop;
            }
            else if(uaccountno < temp->accountno)
            {
                struct record* ptr = (struct record*)malloc(sizeof(struct record));
                if(ptr == NULL)
                {
                    stop = -1;
                    return stop;
                }
                ptr->accountno = uaccountno;
                strncpy(ptr->name, uname, sizeof(ptr->name)-1);
                strncpy(ptr->address, uaddress, sizeof(ptr->name)-1);
                if(previous == NULL)
                {
                    ptr->next = *start;
                    *start = ptr;
                }
                else
                {
                    previous->next = ptr;
                    ptr->next = temp;
                }
                return stop;
            }
            else
            {
            previous = temp;
            temp = temp->next;
            }
        }
    }
    return stop;
}

```
