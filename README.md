# HOSPITAL-MANAGEMENT-SYSTEM
#include<stdio.h>
#include<conio.h>
#include<fstream.h>
#include<stdlib.h>
#include<string.h>
#include<iomanip.h>
//class name: patient
class patient{public:
char name[30];
char blood_group[6];
int pat_id;
long int phn;
int a;
void patientdata();
void showdata(); };
// function to get and show data
void patient::patientdata()
{ cout<<"********************************************************************************************\n";
cout<<"\n\n\t\t\t CREAT NEW PATIENT DATABASE";
cout<<"**********************************************************************************************\n";
cout<<"\n ENTER PATIENT ID \n";
cin>>pat_id;
cout<<"\n ENTER PATIENT NAME \n";
cin>>name;
cout<<"\n ENTER PATIENT BLOOD GROUP \n";
cin>>blood_group;
fflush(stdin);
cout<<"\n ENTER PATIENT PHONE NUMBER \n";
cin>>phn; }
void patient::showdata()
{cout<<"\n PATIENT ID \t:"<<pat_id;
cout<<"\n PATIENT NAME\t:"<<name;
cout<<"\n BLOOD GROUP\t:"<<blood_group;
cout<<"\n PATIENT PHONE NUMBER\t:"<<phn;
cout<<"\n\n"; }
//main function
void main()
{
clrscr();
gotoxy(20,18);
cout<<"\t program developed by:";
gotoxy(28,22);
cout<<"\t PR \n";
gotoxy(25,28);
cout<<"PRESS ANY KEY TO COUNTINUE";
getch();
clrscr();
char s;
patientobj;
z:
fstream f;
f.open("patient",ios::in|ios::out|ios::app|ios::ate|ios::binary);
cout<<"\n________________________________________________________________________________________________________________________ \n";
cout<<"\t\t\t BLOOD GROUP AUTOMATION \n";
cout<<"\n_________________________________________________________________________________________________________________________ \n";
cout<<"\n\t 1. ENTER PATIENT DATABASE";
cout<<"\n\t 2. VIEW PATIENT DATABASE";
cout<<"\n\t 3. MODIFY PATIENT DATABASE";
cout<<"\n\t 4. SEARCH PATIENT DATABASE";
cout<<"\n\t 5.EXIT";
int a;
cout<<"\n\n\n ENTER YOUR CHOICE:";
f.seekg(0);
cin>>a;
char x;
switch(a);
{ // add patient record
case 1:
clscr();
fstream f;
f.open("patient",ios::in|ios::out|ios::ate|ios::app|ios::binary);
char ans;
obj.patientdata();
f.write((char*)&obj,sizeof(obj));
getch();
cout<<"DO YOU WANT TO COUNTINUE? y OR n:";
ans=getchar();
if(ans=='y'||ans=='n')
goto z;
else
break;
//details to show all patient
case 2:
{ cout<<"\n\n";
fstream f;
f.open("patient",ios::in|ios::out|ios::ate|ios::app|ios::binary);
char ans;
f.seekg(0);
int ctr=0;
while(f.read((char*)&obj,sizeof(obj)))
{
ctr=ctr+1;
if(ctr==8){
getchar();
clscr();
ctr=0;}
obj.showdata();
if(f.eof()++1){
break;}}
f.close();
cout<<"DOU YOU WANT TO COUNTINUE? y or n:";
cin>>ans;
if(ans=='y'||and=='Y')
goto z;
else{ exit(1);}} break;
case 3:
{ clscr();
fstream f;
patient obj;
char name[30];
char blood_group[6];
long int phn;
int pat_id;
f.open("patient",ios::in|ios::binary);
cout<<"\n";
cout<<"\n***********************************************************************************************\n";
cout<<"\n MODIFY PATIENT DATABASE \n";
cout<<"\n ***********************************************************************************************\n";
cout<<"\n ENTER PATIENT NAME:";
cin>>name;
do
{
f.read((char*)&obj,sizeof(obj));
if(f.eof()==1){break;}
if(strcmp(obj.name,name)==0){
cout<<"\n\t PATIENT NAME:"<<obj.name;
cout<<"\n\t PATIENT ID:"<<obj.pat_id;
cout<<"\n\t BLOOD GROUT:"<<obj.blood_group;
cout<<"\n\t PATIENT PHONE NUMBER:"<<obj.phn;
getchar();
cout<<endl;
cout<<endl;
cout<<"\n\t ENTER NEW DATABASE";
cout<<"\n\t ENTER PATIENT NAME:";
cin>>name;
cout<<"\n\t ENTER PATIENT ID:";
cin>>pat_id;
cout<<"\n\t BLOOD GROUP:";
cin>>blood_group;
cout<<"\n\t PATIENT PHONE NUMBER:";
cin>>phn;
cout<<"\n\n";
strcpy(obj.name,name);
strcpy(obj.blood_group,blood_group);
obj.a=a;
int l=f.tellg();
f.close();
f.open("patient",ios::out|ios:;binary|ios:;ate);
f.seekg(l-sizeof(obj));
f.write((char*)&obj,sizeof(obj));}}
while(f);
f.close();
cout<<"DO YOU WANT TO CONTINUE? Y OR N:";
ans=getchar();
if(ans=='Y'||ans=='y'){goto z;}else 
break;}
//SEARCHING PATIENT FROM DATABASE
case 4:
{ clrscr();
fstream f;
patient obj;
char name[30];
char blood_group[6];
long int phn;
int pat_id;
f.open("patient",ios::in|ios::binary);
cout<<"\n";
cout<<"\n **************************************************************************************************************** \n";
cout<<"\n ENTER PATIENT NAME:";
cin>>name;
do{f.read((char*)&obj,sizeof(obj));
if(f.eof()==1){break;}
if(strcmp(obj.name,name)==0){
cout<<"\n\t PATIENT NAME:"<<obj.name;
cout<<"\n\t PATIENT ID:"<<obj.pat_id;
cout<<"\n\t BLOOD GROUP:"<<obj.blood_group;
cout<<"\n\t PATIENT PHONE NUMBER:"<<obj.phn;
getchar();
cout<<endl;
strcpy(obj.name,name);
strcpy(obj.blood_group,blood_group);
obj.a=a;
int l=f.tellg();
f.close();
f.open("patient",ios::out|ios::binary|ios::ate);
f.seekg(l-sizeof(obj));
}
else{cout<<"\n\n PATIENT DOES NOT EXIST \n\n\n";}} while(f);
f.close();
cout<<"\n\n DO YOU WANT TO COUNTINUE? y or n:";
ans=getchar();
if(ans=='Y'||ans=='y'){goto z;} else
break;}
case 5:
{
exit(1);}
default:
{
cout<<"\n\t WRONG INPUT"; }
cout<<"\n\n DO YOU WANT TO COUNTINUE? y or n:";
ans=getchar();
clscr();
if(ans=='Y'||ans=='y'){goto z;} else
break;}
getch();}
