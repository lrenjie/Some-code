/*
    名称:stack操作
    时间:2018/10/31 21:40
    作者:lhaoyuan_renjie
    版本:v0.9.5公测
    历史版本:v0.0.1,v0.1.0,v0.1.2,v0.1.5,
             v0.2.0,v0.2.5,v0.3.5,v0.5.1,
             v0.6.5,v0.7.0,v0.7.1,v0.8.1,
             v0.8.5,v0.9.0,v0.9.3
    功能说明:程序指令中输入help;查看
*/
#include<bits/stdc++.h>
using namespace std;
stack<int>s;
vector< vector<int> >v;
int a[100000];
int choose,length;
char command[100];
inline void clear(void)
{
    length=0;
    memset(a,0,sizeof(a));
    for(int i=0;i<length;i++)
    s.pop();
}
inline void put(void)
{
    if(!length)printf("empty");
    int Length=length;
    while(!s.empty() && Length--)
    {
        //cout<<"Check\n";
        a[Length]=s.top();
        s.pop();
        printf("%d",a[Length]);
        if(Length)
        printf("->");
    }
    for(Length=0;Length<length;Length++)
    {
        //cout<<"Check:"<<Length;
        s.push(a[Length]);
    }
    putchar('\n');
    return;
}
void help(void)
{
    printf("------------------------------------help------------------------------------\n");
    printf("   Help   :You can manipulate the stack.\n");
    printf(" Commands :1.list        You can use this to see your stack.\n");
    printf("           2.pop         You can use this to pop some elements.\n");
    printf("                         of your stack.\n");
    printf("           3.push        You can use this to push some elements into\n");
    printf("                         your stack.\n");
    printf("           4.clear       You can use this to clear your stack.\n");
    printf("           5.new random  You can use this to replace your stack with\n");
    printf("                         a new random stack.\n");
    printf("           6.length      You can use this to check the size of your stack.\n");
    printf("           7.help        You can use this to get the helps.\n");
    printf("           8.cls         You can use this to clear the screen.\n");
    printf("           9.exit        You can use this to quit the program.\n");
    printf("          10.push random You can use this to push a new random\n");
    printf("                         element into your stack.\n");
    printf("------------------------------------help------------------------------------\n");
    printf("Want more help?(y/n)");
    char CHOOSE;
    cin>>CHOOSE;
    getchar();
    if(CHOOSE=='y')system("start  https://www.luogu.org/blog/lhaoyuan-renjie/stack-cao-zuo-bang-zhu");
}
int main()
{
    printf("Start With:\n0.empty\n1.random\n");
    scanf("%d",&choose);
    getchar();
    srand((unsigned)time(NULL));
    if(choose)
    {
        printf("Start with a random stack,length:");
        scanf("%d",&length);
        getchar();
        //cout<<"Check:\n";
        for(int i=0;i<length;i++)
        {
            //cout<<"Check1:\n";
            int x=rand()%100;
            //cout<<"Check2:\n";
            s.push(x);
            //cout<<"Check3:\n";
        }
        //cout<<"Check:\n";
    }
    printf("Start:");
    put();
    //cout<<"Check\n";
    printf("If you want some helps,type\"help;\" in your command.\n");
    while(1)
    {
        printf("Input command:");
        gets(command);
        if(command[0]=='\0')
        continue;
        else if(command[strlen(command)-1]!=';')
        {
            printf("[Error]Expected ';' at the end of input.\n");
            continue;
        }
        if(command[0]=='l' && command[1]=='i' && command[2]=='s' && command[3]=='t' && command[4]==';' && command[5]=='\0')
            put();
        else if(command[0]=='p' && command[1]=='o' && command[2]=='p' && command[strlen(command)-1]==';' && command[strlen(command)]=='\0')
        {
            if(command[3]==';')
            {
                if(length>0)
                {
                    length--;
                    s.pop();
                }
                else if(length==0)
                printf("[Error]Your stack is empty.\n");
                else
                {
                    printf("[Error]Your program crashed!\n");
                    system("pause");
                    exit(0);
                }
            }
            else
            {
                int num=0;
                for(int i=4;command[i]!=';';i++)
                {
                    num*=10;
                    num+=command[i]-'0';
                }
                if(num>length)
                printf("[Error]The length of your stack is less than %d !\n",num);
                else
                for(int i=0;i<num;i++)
                {
                    length--;
                    s.pop();
                }
            }
        }
        else if(command[0]=='p' && command[1]=='u' && command[2]=='s' && command[3]=='h' && command[5]>='0' && command[5]<='9' && command[strlen(command)-1]==';' && command[strlen(command)]=='\0')
        {
            length++;
            int j=0;
            int num[100]={};
            for(int i=5;;i++)
            {
                if(command[i]==' ')
                {
                    length--;
                    printf("[Error]Please use ',' to separate numbers.\n");
                    break;
                }
                //cout<<"Check1:\n";
                if(command[i]!=',' && command[i]!=';')
                {
                    //cout<<"Check2:\n";
                    //cout<<"test:command[i]:"<<command[i]-'0'<<'\n';
                    //cout<<"test:j:"<<j<<'\n';
                    num[j]*=10;
                    num[j]+=command[i]-'0';
                }
                else if(command[i]==',')
                {
                    //cout<<"Check3:\n";
                    length++;
                    s.push(num[j]);
                    j++;
                }
                else
                {
                    //cout<<"Check4:\n";
                    s.push(num[j]);
                    j++;
                    break;
                }
            }
        }
        else if(command[0]=='c' && command[1]=='l' && command[2]=='e' && command[3]=='a' && command[4]=='r' && command[5]==';' && command[6]=='\0')
        clear();
        else if(command[0]=='e' && command[1]=='x' && command[2]=='i' && command[3]=='t' && command[4]==';' && command[5]=='\0')
        exit(0);
        else if(command[0]=='n' && command[1]=='e' && command[2]=='w' && command[3]==' ' && command[4]=='r' && command[5]=='a' && command[6]=='n' && command[7]=='d' && command[8]=='o' && command[9]=='m' && command[10]==';' && command[11]=='\0')
        {
            int LENGTH;
            printf("Input the new random stack length:");
            cin>>LENGTH;
            getchar();
            srand((unsigned)time(NULL));
            //cout<<"Check:\n";
            clear();
            //cout<<"Check:\n";
            //cout<<LENGTH;
            srand((unsigned)time(NULL));
            for(int i=0;i<LENGTH;i++)
            {
                length++;
                //cout<<"Check1:\n";
                int x=rand()%100;
                //cout<<"Check2:\n";
                s.push(x);
                //cout<<"Check3:\n";
            }
            //cout<<i;
            //cout<<"Check:\n";
        }
        else if(command[0]=='l' && command[1]=='e' && command[2]=='n' && command[3]=='g' && command[4]=='t' && command[5]=='h' && command[6]==';' && command[7]=='\0')
        printf("The length of your stack is:%d.\n",length);
        else if(command[0]=='h' && command[1]=='e' && command[2]=='l' && command[3]=='p' && command[4]==';' && command[5]=='\0')
        help();
        else if(command[0]=='c' && command[1]=='l' && command[2]=='s' && command[3]==';' && command[4]=='\0')
        system("cls");
        else if(command[0]=='p' && command[1]=='u' && command[2]=='s' && command[3]=='h' && command[4]==' ' && command[5]=='r' && command[6]=='a' && command[7]=='n' && command[8]=='d' && command[9]=='o' && command[10]=='m' && command[11]==';' && command[12]=='\0')
        {
            length++;
            //cout<<"Check1:\n";
            int x=rand()%100;
            //cout<<"Check2:\n";
            s.push(x);
            //cout<<"Check3:\n";
        }
        else printf("[Error]No such command named \"%s\".\n",command);
    }
}
