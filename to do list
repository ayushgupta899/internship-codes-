#include <iostream>
#include <fstream>
#include<string>
#include <cstdlib>

using namespace std;
int ID;

struct todo {
    int id;
    string task;
};

void addtodo() {
    
	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    todo todo;
    cout << "Enter new task: "<<endl;
    cin.get();
    getline(cin, todo.task);
    ID++;

    
    ofstream write;
    write.open("todo.txt", ios::app);
    write << "\n" << ID;
    write << "\n" << todo.task ;
    write.close();


    write.open("id.txt");
    write << ID;
    write.close();

    char ch;
    cout<<"Do you want to add more task? y/n"<<endl;
    cin>> ch;


    if(ch == 'y'){
        addtodo();
    }
    else{
        cout << "Task has been added successfully"<<endl;
        return;
    }
}


void print(todo s) {
    cout << "ID is : " << s.id<<endl;
    cout << "Task is : " << s.task<<endl;
}


void readData() {

	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    todo todo;
    ifstream read;
    read.open("todo.txt");
    cout <<" Your current Tasks in the list "<<endl;
    
    
    while (!read.eof()) {
        read >> todo.id;
        read.ignore();
        getline(read, todo.task);
        print(todo);
    }
    read.close();
}


int searchData() {

	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    int id;
    cout << "Enter task id: "<<endl;
    cin >> id;
    todo todo;
    ifstream read;
    read.open("todo.txt");
    
    
    while (!read.eof()) {
        read >> todo.id;
        read.ignore();
        getline(read, todo.task);
        if (todo.id == id) {
            print(todo);
            return id;
        }
    }
}


void deleteData() {

	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    int id = searchData();
    cout << "Do you want to delete this task (y/n) : "<<endl;
    char choice;
    cin >> choice;
    if (choice == 'y') {
        todo todo;
        ofstream tempFile;
        tempFile.open("temp.txt");
        ifstream read;
        read.open("todo.txt");
 
 
        while (!read.eof()) {
            read >> todo.id;
            read.ignore();
            getline(read, todo.task);
            if (todo.id != id) {
                tempFile << "\n" << todo.id;
                tempFile << "\n" << todo.task;
            }
        }
        read.close();
        tempFile.close();
        remove("todo.txt");
        rename("temp.txt", "todo.txt");
        cout << "Task deleted successfuly"<<endl;
    }
    else {
        cout << "Record not deleted"<<endl;
    }
}

void updateData() {
    
	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    int id = searchData();
    cout << "You want to update this task (y/n) : "<<endl;
    char choice;
    cin >> choice;
    if (choice == 'y') {
        todo newData;
        cout << "Enter todo task : "<<endl;
        cin.get();
        getline(cin, newData.task);
        todo todo;
        ofstream tempFile;
        tempFile.open("temp.txt");
        ifstream read;
        read.open("todo.txt");
        
        
        while (!read.eof()) {
            read >> todo.id;
            read.ignore();
            getline(read, todo.task);
            if (todo.id != id) {
                tempFile << "\n" << todo.id;
                tempFile << "\n" << todo.task;
            }
            else {
                tempFile << "\n"<< todo.id;
                tempFile << "\n"<< newData.task;
            }
        }
        read.close();
        tempFile.close();
        remove("todo.txt");
        rename("temp.txt", "todo.txt");
        cout << "Task updated successfuly"<<endl;
    }
    else {
        cout << "Record not deleted"<<endl;
    }
}
int main()
{
	cout<<" Welcome To Your ToDo List "<<endl;
    cout<<endl;
    
    ifstream read;
    read.open("id.txt");
    if (!read.fail()) {
        read >> ID;
    }
    else {
        ID = 0;
    }
    read.close();

    while (true) {
        cout<<endl<<endl;
        cout << "1.Add data" <<endl;
        cout << "2.See data" <<endl;
        cout << "3.Search data" <<endl;
        cout << "4.Delete data" <<endl;
        cout << "5.Update data" <<endl;

        int choice;
        cout<< " Enter choice : "<<endl;
        cin >> choice;
        switch (choice) {
        case 1:
            addtodo();
            break;
        case 2:
            readData();
            break;
        case 3:
            searchData();
            break;
        case 4:
            deleteData();
            break;
        case 5:
            updateData();
            break;
        }
    }

}
