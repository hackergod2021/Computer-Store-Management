# Computer-Store-Management
Computer Store Management using  C++ in DEV C++

PROGRAMMED BY- ANKAN PAUL 

REVISED AND DESIGNED BY – Riya Jana

#Daily Summary

// Function to display Daily Summary
// Time Complexity - O(n^2)
void computerType ::daily_summary()
{
    int i, num;
    string str = "\t\t===========================================\n";

    system("cls");
    node *temp;

    temp = start_ptr;

    if (temp == NULL) // Invalid receipt code
    {
        cout << endl << str;
        cout << "\t\t\tThere is no Order to show!!!\n\t\t\tThe List is Empty\n";
        cout << str << endl;
    }

    else
    {
        cout << "\n";
        cout << "================================================================================================" << endl;
        cout << " \t\t\tHere is the Daily Summary of All Orders \n"; //print all receipt
        cout << "================================================================================================\n"
             << endl;

        while (temp != NULL)
        {

            cout << "Receipt Number : " << temp->receipt_number << endl;
            cout << "Customer Name  : " << temp->customerName << endl;
            cout << "Order Date     : " << temp->date << endl
                 << endl;

            cout << "+===================+==============================+====================+=======================+" << endl;
            cout << "|   Computer Type   |         Computer Name        |      Quantity      |     Total Price (Rs.) |" << endl;
            cout << "+===================+==============================+====================+=======================+" << endl;

            for (i = 0; i < temp->x; i++)
            {
                cout << "\t" << temp->type[temp->menu2[i] - 1] << "  \t\t";
                cout << " " << temp->computerName[temp->menu2[i] - 1] << "\t  ";
                cout << "\t    " << temp->quantity[i] << "\t";
                cout << "\t\t" << temp->amount[i] << ".00" << endl;
                cout << "+-------------------+------------------------------+--------------------+-----------------------+" << endl;
            }

            temp->total = temp->amount[0] + temp->amount[1] + temp->amount[2] + temp->amount[3] + temp->amount[4] + temp->amount[5] + temp->amount[6] + temp->amount[7] + temp->amount[8] + temp->amount[9];
            cout << "\nTotal Bill is : " << "Rs. " << temp->total << ".00/-\n";

            cout << "\n=================================================================================================\n"
                 << endl;

            temp = temp->next;
        }
    }

} // End daily summary






#Delete order





// Function to delete order
// Time Complexity - O(n)
void computerType ::delete_order()
{
    system("cls");

    string str = "\t===========================================\n";

    if (start_ptr == NULL)
    {
        cout << endl;
        cout << str;
        cerr << "\t     Can not delete from an Empty List\n";
        cout << str;
        cout << endl;
    }

    else
    {
        int i, num, count;
        cout << "\nEnter the receipt numnber you want to delete: ";
        cin >> num;
        node *q;
        node *temp;
        bool found = false;

        if (start_ptr->receipt_number == num)
        {
            q = start_ptr;
            start_ptr = start_ptr->next;

            count--;

            if (start_ptr == NULL)
                last = NULL;

            delete q;

            cout << "\n\t\t========================================\n";
            cout << "\t\t The Receipt is Deleted Successfully!!!" << endl;
            cout << "\t\t========================================\n\n";
        }

        else
        {
            temp = start_ptr;
            q = start_ptr->next;

            while ((!found) && (q != NULL))
            {
                if (q->receipt_number != num)
                {
                    temp = q;
                    q = q->next;
                }

                else
                    found = true;
            }

            if (found)
            {
                temp->next = q->next;
                count--;

                if (last == q)
                    last = temp;
                delete q;

                cout << "\n\t\t========================================\n";
                cout << "\t\t The Receipt is Deleted Successfully!!!" << endl;
                cout << "\t\t========================================\n\n";
            }

            else
            {
                cout << "\n\t\t==========================================\n";
                cout << "\t\t Item to be deleted is not in the list!!!" << endl;
                cout << "\t\t==========================================\n\n";
            }
        }
    }

} // End function delete_order




#Display reciept




// Function to delete order
// Time Complexity - O(n)
void computerType ::delete_order()
{
    system("cls");

    string str = "\t===========================================\n";

    if (start_ptr == NULL)
    {
        cout << endl;
        cout << str;
        cerr << "\t     Can not delete from an Empty List\n";
        cout << str;
        cout << endl;
    }

    else
    {
        int i, num, count;
        cout << "\nEnter the receipt numnber you want to delete: ";
        cin >> num;
        node *q;
        node *temp;
        bool found = false;

        if (start_ptr->receipt_number == num)
        {
            q = start_ptr;
            start_ptr = start_ptr->next;

            count--;

            if (start_ptr == NULL)
                last = NULL;

            delete q;

            cout << "\n\t\t========================================\n";
            cout << "\t\t The Receipt is Deleted Successfully!!!" << endl;
            cout << "\t\t========================================\n\n";
        }

        else
        {
            temp = start_ptr;
            q = start_ptr->next;

            while ((!found) && (q != NULL))
            {
                if (q->receipt_number != num)
                {
                    temp = q;
                    q = q->next;
                }

                else
                    found = true;
            }

            if (found)
            {
                temp->next = q->next;
                count--;

                if (last == q)
                    last = temp;
                delete q;

                cout << "\n\t\t========================================\n";
                cout << "\t\t The Receipt is Deleted Successfully!!!" << endl;
                cout << "\t\t========================================\n\n";
            }

            else
            {
                cout << "\n\t\t==========================================\n";
                cout << "\t\t Item to be deleted is not in the list!!!" << endl;
                cout << "\t\t==========================================\n\n";
            }
        }
    }

} // End function delete_order





#exit






// Function to exit the program
void computerType ::exit()
{

    cout << "\nYou chose to Exit.\n"
         << endl;

} // End function exit





#Header 





#include <iostream>
#include <bits/stdc++.h>

using namespace std;
  
  
  
  
  
  #Modify order

  
  
  
  
  
  // Function to modify order
// Time Complexity - O(n^2)
void computerType ::modify()
{
    system("cls");
    int i, ch, sid;
    bool found = false;
    temp = start_ptr;

    if (temp == NULL || sid == 0)
    {
        cout << "\n\t\t=============================\n";
        cout << "\t\t    NO RECORD TO MODIFY...!\n";
        cout << "\t\t=============================\n\n";
    }

    else
    {
        cout << "\nEnter Receipt Number To Modify: ";
        cin >> sid;

        while (temp != NULL && !found)
        {
            if (temp->receipt_number == sid)
                found = true;

            else
                temp = temp->next;

            if (found)
            {
                cout << "Change Order Number: ";
                cin >> temp->receipt_number;

                cout << "Change Customer Name: ";
                cin >> temp->customerName;

                cout << "Change Date : ";
                cin >> temp->date;

                cout << "\nHow many new laptops would you like to change" << endl;
                cout << "(Maximum is 10 order for each transaction): ";
                cin >> temp->x;

                if (temp->x > 10)
                {
                    cout << "The laptop you order is exceed the maximum amount of order!";
                    system("pause");
                }

                else
                {
                    for (i = 0; i < temp->x; i++)
                    {
                        cout << "-----------------------------------------\n";
                        cout << "\nPlease Enter your selection to Change: ";
                        cin >> temp->menu2[i];

                        cout << "Change Laptop Name: " << temp->computerName[temp->menu2[i] - 1] << endl;

                        cout << "\nHow many New laptops do you want: ";
                        cin >> temp->quantity[i];
                        cout << "\n-----------------------------------------\n";

                        temp->amount[i] = temp->quantity[i] * temp->computer[temp->menu2[i] - 1];

                        cout << "\n----------------------------------------------------------------\n";
                        cout << "The amount you need to pay after modification is: " << "Rs. " << temp->amount[i] << ".00/-\n";
                        cout << "----------------------------------------------------------------\n\n"; 

                        system("PAUSE");
                    }

                    temp = temp->next;

                    system("cls");
                }

                cout << "\n\t\t=============================\n";
                cout << "\t\t     RECORD MODIFIED....!" << endl;
                cout << "\t\t=============================\n\n";
            }

            else
            {
                if (temp != NULL && temp->receipt_number != sid)
                {
                    cout << "\n\t\t===============================\n";
                    cout << "\t\t   Invalid Receipt Number...!" << endl;
                    cout << "\t\t===============================\n\n";
                }
            }
        }
    }

} // End modify function
  
  
  
  
  
  
  #Project
  
  
  
  
  
  
  #include "Class.cpp"
#include "Structure.cpp"
#include "TakeOrder.cpp"
#include "DeleteOrder.cpp"
#include "DisplayReceipt.cpp"
#include "ModifyOrder.cpp"
#include "DailySummary.cpp"
#include "Exit.cpp"

int main() // main function
{
    // Create an object of class computerType
    computerType computer;

    int menu;

    do
    {
        system("cls");

        cout << "\t\t==================================================\n";
        cout << "\t\t\t Computer Store Management System \n";
        cout << "\t\t==================================================\n\n";
        cout << "\t\t---------------------------------------------------\n";
        cout << "\t\t||\t1. Take New Computer Order \t\t ||\n";
        cout << "\t\t||\t2. Delete Latest Order\t\t\t ||\n";
        cout << "\t\t||\t3. Modify Order List \t\t\t ||\n";
        cout << "\t\t||\t4. Print the Receipt                  \t ||\n";
        cout << "\t\t||\t5. Daily Summary of Total Sale \t\t ||\n";
        cout << "\t\t||\t6. Exit\t\t\t\t\t ||\n";
        cout << "\t\t---------------------------------------------------\n";

        cout << "\nEnter Choice: ";
        cin >> menu;

        switch (menu)
        {
        case 1:
        {
            computer.take_order(); // Function add
            break;
        } // End case 1

        case 2:
        {
            computer.delete_order(); // Function delete
            system("PAUSE");
            break;
        } // End case 2

        case 3:
        {
            computer.modify(); // Function modify
            system("PAUSE");
            break;
        } // End case 3

        case 4:
        {
            computer.order_list(); // Function order
            system("PAUSE");
            break;
        } // End case 4
        case 5:
        {
            computer.daily_summary(); // Function daily_summary
            system("PAUSE");
            break;
        } // End case 5

        case 6:
        {
            computer.exit(); // Function exit
            goto a;
            break;
        } // End case 6

        default:
        {
            cout << "Invalid input\nPlease re-enter the input\n"
                 << endl;
        } // End default

        } // End Switch

    } while (menu != 6); // End do

a: // goto

    cout << "\t\t===========================\n";
    cout << "\t\t\tThank You!!!\n";
    cout << "\t\t===========================\n\n";

    system("PAUSE");

    return 0;

} // End main function


////////////////////////////END OF THE PROGRAM//////////////////////////////////////////
  
  
  
  
  
  #Structure
  
  
  
  
  
  
  #include "Header.cpp"

//Construct node
struct node
{
    int receipt_number, x;

    string customerName, date;

    int quantity[10], menu2[10];

    int amount[10], total;

    string type[10] = {"8GB", "4GB", "4GB", "8GB", "8GB", "8GB", "4GB", "8GB", "4GB", "8GB"};

    string specifications[10] = {"Intel Core i5(10th Gen)", "Intel Core i3 (10th Gen)", "Intel Core i5(8th Gen)", "Intel Core i5 (8th Gen)", "macOS Catalina", "Intel Core i5(10th Gen)", "Intel Core i3(5th Gen)", "Intel Core i3(7th Gen)", "Intel Core i5(6th Gen)", "Intel Core i7(10th Gen)"};

    string computerName[10] = {"Dell Inspiron 15 5590", "Asus X412FA-EK361T", "Lenovo Ideapad 330", "Huawei Mach-W19B", "Apple MacBook Air", "HP 15s-du1034tu", "Acer Aspire ES1-571", "HP 15-DA0070TX ", "Lenovo Ideapad 300", "HP Pavilion 15-ac028TX"};

    int computer[10] = {66490, 40000, 44000, 77899, 118990, 53999, 25655, 49279, 43000, 64000};

    // node *prev;
    node *next;

} *q, *temp; // Pointer declaration

node *start_ptr = NULL;
node *head = NULL;
node *last = NULL;
  
  
  
  
  
  
  #Take order
  
  
  
  
  
  
  
  // Function to take order
// Time Complexity - O(n)
void computerType ::take_order()
{
    system("cls");
    int i;
    int choice, quantity, price, None;
    string str1 = "****************************************\n";
    string str2 = "+-------+-----------------+---------------------------------+------------------------------+-----------------------+\n";

    cout << "-----------------";
    cout << "\nAdd Order Details\n";
    cout << "-----------------\n\n";

    node *temp;
    temp = new node;

    cout << str1;
    cout << " ID "
         << "\t   COMPUTER TYPE"
         << "\t COMPUTER SPECS"
         << "   \t\t COMPUTER NAME"
         << "    \t\tCOMPUTER PRICE (RS.)" << endl;
    cout << str1;
    cout << "0001"
         << "\t"
         << "\t8GB"
         << "\t\t"
         << " Intel Core i5(10th Gen)"
         << "\t"
         << " Dell Inspiron 15 5590  "
         << "  	66490.00" << endl;
    cout << str2;
    cout << "0002"
         << "\t"
         << "\t4GB"
         << "\t\t"
         << " Intel Core i3(10th Gen)"
         << "\t"
         << " Asus X412FA-EK361T     "
         << "	40000.00" << endl;
    cout << str2;
    cout << "0003"
         << "\t"
         << "\t4GB"
         << "\t\t"
         << " Intel Core i5(8th Gen) "
         << "\t"
         << " Lenovo Ideapad 330     "
         << "	44000.00" << endl;
    cout << str2;
    cout << "0004"
         << "\t"
         << "\t8GB"
         << "\t\t"
         << " Intel Core i5 (8th Gen)  "
         << "\t"
         << " Huawei Mach-W19B"
         << "       \t77899.00" << endl;
    cout << str2;
    cout << "0005"
         << "\t"
         << "\t8GB"
         << "\t\t"
         << " macOS Catalina         "
         << "\t"
         << " Apple MacBook Air      "
         << "	118990.00" << endl;
    cout << str2;
    cout << "0006"
         << "\t"
         << "\t8GB"
         << "\t\t"
         << " Intel Core i5(10th Gen)"
         << "\t"
         << " HP 15s-du1034tu        "
         << " 	53999.00" << endl;
    cout << str2;
    cout << "0007"
         << "\t"
         << "\t4GB"
         << "\t\t"
         << " Intel Core i3(5th Gen) "
         << "\t"
         << " Acer Aspire ES1-571    "
         << "	25655.00" << endl;
    cout << str2;
    cout << "0008"
         << "\t"
         << "\t4GB"
         << "\t\t"
         << " Intel Core i3(7th Gen) "
         << "\t"
         << " HP 15-DA0070TX           "
         << "	49279.00" << endl;
    cout << str2;
    cout << "0009"
         << "\t"
         << "\t4GB"
         << "\t\t"
         << " Intel Core i5(6th Gen) "
         << "\t"
         << " Lenovo Ideapad 300     "
         << "        43000.00" << endl;
    cout << str2;
    cout << "0010"
         << "\t"
         << "\t8GB"
         << "\t\t"
         << " Intel Core i7(5th Gen) "
         << "\t"
         << " HP Pavilion 15-ac028TX "
         << "	64000.00" << endl;
    cout << str1;
    cout << " " << endl;

    temp = new node;

    string str = "-------------------------------------------\n";

    cout << str;

    cout << "Type Order No: ";
    cin >> temp->receipt_number;

    cout << "Enter Customer Name: ";
    cin >> temp->customerName;

    cout << "Enter Date: ";
    cin >> temp->date;

    cout << str;

    cout << "\nHow many different laptops would you like to order?";
    cout << "\n(Maximum order is 10 for each transaction): ";
    cin >> temp->x;

    cout << endl;

    if (temp->x <= 0)
    {
         cout << "\nInvalid order!!!\n";
         cout << str;
         system("pause");
    }

    else if (temp->x > 10)
    {
        cout << "\nYour order exceeds the maximum amount of order!!!\n"; 
        cout << str;
        system("pause");
    }

    else
    {
         cout << str;
         
         cout << "\t    Enter Computer ID\n";

         for (i = 0; i < temp->x; i++)
         {
              cout << str;

              cout << "Please Enter Your Selection: ";
              cin >> temp->menu2[i];

              cout << "\nLaptop Name: " << temp->computerName[temp->menu2[i] - 1] << endl;

              cout << "\nHow many laptops do you want?: ";
              cin >> temp->quantity[i];

              temp->amount[i] = temp->quantity[i] * temp->computer[temp->menu2[i] - 1];
              cout << "\nThe amount You need to pay is: Rs. " << temp->amount[i] << "/-" << endl;

              cout << str << endl;

              system("PAUSE");
        }

        cout << "\n===========================================================================" << endl;
        cout << "                     Order Taken Successfully..." << endl;
        cout << "===========================================================================" << endl;
        cout << "                Go to Receipt Menu to Pay The Bill" << endl;
        cout << "===========================================================================\n" << endl;

        system("PAUSE");

        temp->next = NULL;

        if (start_ptr != NULL)
            temp->next = start_ptr;

        start_ptr = temp;

        system("cls");
    }

} // End function take_order
  
  
  
  
  
  
  
  
# Computer-Store-Management
Computer Store Management using  C++ in DEV C++

PROGRAMMED BY- ANKAN PAUL   
  
  
  
  
  
  
  
  
  
  







