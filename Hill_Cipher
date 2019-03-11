#include <iostream>
#include <stdio.h>
#include <stdlib.h>
#include<string>
#include<math.h>
using namespace std;

int main()
{
   long long  Length=0;
   long long pos=0,counter=0;
    string s1,s2;
    string MatrixNums,Letter;
    string planText,Decryption="";
    string letters[]={"A","B","C","D","E","F","G","H","I","J","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z"};
   // getline(cin,no);
   // cout<<"yes";
    //Length=atoi(no.c_str());

   scanf("%d ",&Length);
   //cout<<Length<<endl;
   //cin>>Length;
   long long sqrtno=sqrt(Length);
   long long** key = new long long*[sqrtno];
    for(long long i = 0; i < sqrtno; ++i)
        key[i] = new long long[sqrtno];

    //cout<<"///"<<sqrtno;
    getline(cin,MatrixNums);
    getline(cin,planText);
    counter=(MatrixNums.length()/2)+1;

        for(long long i=0;i<(sqrtno);i++)
            {
            for(long long j=0;j<(sqrtno);j++)
                {
                pos = MatrixNums.find(" ");
                Letter = MatrixNums.substr(0, pos);
                 key[i][j] = atoi(Letter.c_str());
                //cout << Letter << endl;
                MatrixNums.erase(0, pos +1);
                counter--;
                //cout<<"counter= "<<counter<<endl;
                }
            }
   // cout<<"MatrixNums= "<<MatrixNums<<"counter= "<<counter<<endl;


/*
 for(int i=0;i<(sqrtno);i++)
    {
        for(int j=0;j<(sqrtno);j++)
        {
            cout<<key[i][j]<<"  ";
        }
        cout<<endl;
    }*/
     long long** portion = new long long*[sqrtno];
     long long** result = new long long*[sqrtno];
    for(long i = 0; i < sqrtno; ++i){
        portion[i] = new long long[1];
        result[i]= new long long[1];
        }
//cout<<"Length-planText.length()="<<Length-planText.length()<<endl;
    if(planText.length()%sqrtno!=0){
        while(planText.length()%sqrtno!=0){
            planText.insert(planText.length(),"X");
            // cout<<"*";
        }
            }

       // cout<<"planText="<<planText<<endl;
while(planText.length()>0){
    for(long long i=0;i<sqrtno;i++)
    {
        for(long long j=0;j<26;j++)
        {
            s1=planText[i];
            s2=letters[j];
            if(s1==s2)
            portion[i][0]=j;
            result[i][0]=0;
        }
    }

    for(long long i=0;i<sqrtno;i++)
    {
        for(long long j=0;j<sqrtno;j++)
        {
            result[i][0]=result[i][0]+key[i][j]*portion[j][0];
        }
    }
for(long long i=0;i<(sqrtno);i++)
    {
        while(result[i][0]>25)
            result[i][0]=(result[i][0])%26;
   // cout<<result[i][0]<<endl;
    }
for(long long i=0;i<sqrtno;i++)
{
    for(long long j=0;j<26;j++)
    {
        if(result[i][0]==j)
            Decryption=Decryption+letters[j];
    }
}
planText.erase(0,sqrtno);
//cout<<planText<<endl;
}
cout<<Decryption<<endl;
    for(long long i = 0; i < (sqrtno); ++i)
    {
        delete[] key[i];
    }
    delete[] key;
    for(long long i = 0; i < sqrtno; ++i)
    {
        delete[] portion[i];
        delete[] result[i];
    }
    delete[] portion;
    delete[] result;

    return 0;
}
