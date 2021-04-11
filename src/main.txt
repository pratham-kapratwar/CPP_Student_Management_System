#include<iostream>
#include<conio.h>
#include<windows.h>

using namespace std;
struct stu{
	string name,id,address;
	int semester;
	long long contact;
};
int total=0;
stu e[100];
void studata(){
	int user=0;
	cout<<"\nHow many Students data do you want to enter : ";
	cin>>user;
	for(int i=total;i<total+user;i++){
		cout<<"\n Enter data of Student : "<<i+1<<endl<<endl;
		cout<<"\nEnter student name : ";
		cin>>e[i].name;
		cout<<"\nEnter student id : ";
		cin>>e[i].id;
		cout<<"\nEnter student address : ";
		cin>>e[i].address;
		cout<<"\nEnter student contact : ";
		cin>>e[i].contact;
		cout<<"\nEnter student semester : ";
		cin>>e[i].semester;
	}
	total=total+user;
}
void show(){
	if(total!=0){
	for(int i=0;i<total;i++){
		cout<<"\nData of Student : "<<i+1<<endl;
		cout<<"\nName : "<<e[i].name<<endl;
		cout<<"ID : "<<e[i].id<<endl;
		cout<<"Address : "<<e[i].address<<endl;
		cout<<"Contact : "<<e[i].contact<<endl;
		cout<<"Semester : "<<e[i].semester<<endl;
	}
    }
    else{
    	cout<<"\nNo data is entered"<<endl;
	}
}
void search(){
	if(total!=0){
	string id;
	cout<<"\nEnter id of student which you want to search : ";
	cin>>id;
	for(int i=0;i<total;i++){
		if(e[i].id==id){
		cout<<"\nData of Student : "<<i+1<<endl;
		cout<<"\nName : "<<e[i].name<<endl;
		cout<<"ID : "<<e[i].id<<endl;
		cout<<"Address : "<<e[i].address<<endl;
		cout<<"Contact : "<<e[i].contact<<endl;
		cout<<"Semester : "<<e[i].semester<<endl;
		break;
		}
		if(i==total-1){
			cout<<"\nNo such record found"<<endl;
		}
	}
}else{
	cout<<"\nNo data is entered"<<endl;
}
}
void update(){
	if(total!=0){
	string id;
	cout<<"\nEnter id of student which you want to update : ";
	cin>>id;
	for(int i=0;i<total;i++){
		if(e[i].id==id){
		cout<<"\nOld data of student "<<i+1<<endl;
		cout<<"\nName : "<<e[i].name<<endl;
		cout<<"ID : "<<e[i].id<<endl;
		cout<<"Address : "<<e[i].address<<endl;
		cout<<"Contact : "<<e[i].contact<<endl;
		cout<<"Semester : "<<e[i].semester<<endl;
		cout<<"\n\nEnter new data : "<<endl;
		cout<<"\nEnter student name: ";
		cin>>e[i].name;
		cout<<"\nEnter student id: ";
		cin>>e[i].id;
		cout<<"\nEnter student address: ";
		cin>>e[i].address;
		cout<<"\nEnter student contact: ";
		cin>>e[i].contact;
		cout<<"\nEnter student semester: ";
		cin>>e[i].semester;
		break;
		}
		if(i==total-1){
			cout<<"\nNo such record found"<<endl;
		}
	}
}else{
	cout<<"\nNo data is entered"<<endl;
}
}
void del(){
	if(total!=0){
	int press;
	cout<<"\nPress 1 to delete specific record,"<<endl;
	cout<<"Press 2 to delete full record"<<endl;
	cin>>press;
	if(press==1){
		string id;
		cout<<"\nEnter id of student which you want to delete : ";
		cin>>id;
		for(int i=0;i<total;i++){
			if(e[i].id==id){
				e[i].name=e[i+1].name;
				e[i].id=e[i+1].id;
				e[i].address=e[i+1].address;
				e[i].contact=e[i+1].contact;
				e[i].semester=e[i+1].semester;
				total--;
				cout<<"\nYour required record is deleted"<<endl;
				break;
			}
			if(i==total-1){
			cout<<"\nNo such record found"<<endl;
		}
		}
	}
	else if(press==2){
		total=0;
		cout<<"\nAll record is deleted"<<endl;
	}
	else{
		cout<<"\nInvalid Input"<<endl;
	}
}else{
	cout<<"\nNo data is entered"<<endl;
}
}
main(){
	cout<<"\n\n\t\t*** Student Management System ***"<<endl;
	  string username,password;
    cout<<"\n\n\n\t\t--- SIGN UP PAGE ---"<<endl;
	cout<<"\n\n\t\tEnter new username : ";
	cin>>username;
	cout<<"\n\t\tEnter new password : ";
	cin>>password;
	cout<<"\n\n\t\tYour new id is creating please wait";
	for(int i=0;i<6;i++)
	{
		cout<<".";
		Sleep(500);
	}
	cout<<"\n\n\n\t\tYour id created successfully!!!";
	Sleep(2000);
	start:
	system("CLS");
	string usrn,pswd;
	cout<<"\n\n\t\t*** Student Management System ***"<<endl;
	cout<<"\n\n\n\t\t--- LOG IN PAGE ---"<<endl;
	cout<<"\n\n\t\tEnter username : ";
	cin>>usrn; 
	cout<<"\n\t\tEnter password : ";
	cin>>pswd;
	Sleep(700);
	
	
	if(usrn==username&&pswd==password)
	{
	 cout<<"\n\n\n\t\tLogged in successful!!!";
	for(int i=0;i<6;i++)
	{
		cout<<".";
		Sleep(1000);
	}
	
	system("CLS");
	char ch;
	while(1){
	cout<<"\n____________________________";
	cout<<"\n\n1 -> Enter data"<<endl;
	cout<<"2 -> Show data"<<endl;
	cout<<"3 -> Search data"<<endl;
	cout<<"4 -> Update data"<<endl;
	cout<<"5 -> Delete data"<<endl;
	cout<<"6 -> Logout account"<<endl;
	cout<<"7 -> Exit"<<endl;
	cout<<"\nEnter Your Choice : ";
	ch=getch();
	system("CLS");
	switch(ch){
		case '1':
			studata();
			break;
		case '2':
			show();
			break;
		case '3':
			search();
			break;
		case '4':
			update();
			break;
		case '5':
			del();
			break;
		case '6':
			goto start;
			break;
		case '7':
			exit(0);
			break;
		default:
			cout<<"\a\nInvalid Input,Please give a proper input!!!"<<endl;
			break;
	}
}
}
  else if(usrn!=username)
  {
  	cout<<"\n\n\t\t\aInvalid username please try again";
  	Sleep(500);
  	for(int i=0;i<6;i++)
	{
		cout<<".";
		Sleep(500);
	}
  	goto start;
  }
  else if(pswd!=password)
  {
  	cout<<"\n\n\t\t\aInvalid password please try again";
  	Sleep(500);
  	for(int i=0;i<6;i++)
	{
		cout<<".";
		Sleep(500);
	}
  	goto start;
  }
  else{
  	cout<<"\n\n\t\t\aInvalid username and password";
  	Sleep(500);
  	goto start;
  }
}