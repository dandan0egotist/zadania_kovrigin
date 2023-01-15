#include <iostream>
using namespace std;
class mString{
    private:
    char *st;
    
    public:
    mString(){
        st=NULL;
    }
    void test(){
        st = new char(10);
        char c = 'a';
        for (int i=0;i<10;i++) st[i]=c++;
        st[9]='\0';
        cout<<st;
    }
    ~mString(){
        if (st){delete st;}
    }
    
    void operator= (const mString& s);
    void operator= (const char* s);
    void operator= (const char s);
    void operator= (const int n);
    
    
    mString operator+ (const mString& s) const;
    mString operator+ (const char* s) const;
    friend mString operator+ (const char * s1,const mString &s);
    
    
    
    friend bool operator>(const mString &s1,const mString &s2);
    friend bool operator>=(const mString &s1,const mString &s2);
    friend bool operator<(const mString &s1,const mString &s2);
    friend bool operator<=(const mString &s1,const mString &s2);
    friend bool operator==(const mString &s1,const mString &s2);
    friend bool operator!=(const mString &s1,const mString &s2);
    
    friend std::ostream& operator<< (std::ostream &out, const mString &s);
    friend std::istream& operator>> (std::istream &in, mString &s);
    
    int length();
    mString substr(int start,int count);
    mString replace(mString s1,mString s2);
    int find(mString &s);
    
};
std::ostream& operator<< (std::ostream &out, const mString &s){
    cout<<s.st;
    return out;
}
std::istream& operator>> (std::istream &in, mString &s){
    char buf[10000],t;
    int i,k=0;
    t=in.get();
    while ((int)(t)!=10){
        buf[k++]=t;
        t=in.get();
    }
    if (s.st) delete s.st;
    s.st = new char[k+1];
    for (i=0;i<k;i++) s.st[i]=buf[i];
    s.st[i]='\0';
    return in;
}
void mString::operator= (const mString& s){
    if (st) delete st;
    int i,k=0;
    while(s.st[k++]);
    st=new char[k+1];
    for (int i=0;i<k;i++)st[i]=s.st[i];
    st[i]='\0';
}
void mString::operator= (const char s){
    if (st) delete st;
    int i,k=0;
    st=new char[2];
    st[0]=s;
    st[1]='\0';
}
void mString::operator= (const int n){
    if (st) delete st;
    int i,k=0,t=n,o;
    while (t){
        t/=10;
        k++;
    }
    st=new char[k+1];
    
    t=n;i=k-1;
    while (t){
        o=t%10;
        st[i]='0'+o;
        t/=10;
        i--;
    }
    st[k]='\0';
}
mString mString::operator+ (const mString& s) const
{
    mString res;
    int i,k=0,k1=0,k2=0;
    while(st[k1++]);
    k1--;
    while (s.st[k2++]);
    k2--;
    res.st= new char[k1+k2+1];
    for(i=0;i<k1;i++) res.st[k++]=st[i];
    for(i=0;i<k2;i++) res.st[k++]=s.st[i];
    
    res.st[k]='\0';
    return res;
}
mString mString::operator+ (const char* s) const{
    mString res;
    int i,k=0,k1=0,k2=0;
    while(st[k1++]);
    k1--;
    while (s[k2++]);
    k2--;
    res.st= new char[k1+k2+1];
    for(i=0;i<k1;i++) res.st[k++]=st[i];
    for(i=0;i<k2;i++) res.st[k++]=s[i];
    
    res.st[k]='\0';
    return res;
}
void mString::operator= (const char* s){
    if (st) delete st;
    int i,k=0;
    while(s[k++]);
    st=new char[k+1];
    for (int i=0;i<k;i++)st[i]=s[i];
    st[i]='\0';
}
mString operator+ (const char * s1,const mString &s){
    mString res;
    int i,k=0,k1=0,k2=0;
    while(s1[k1++]);
    k1--;
    while (s.st[k2++]);
    k2--;
    res.st= new char[k1+k2+1];
    for(i=0;i<k1;i++) res.st[k++]=s1[i];
    for(i=0;i<k2;i++) res.st[k++]=s.st[i];
    
    res.st[k]='\0';
    return res;
}
mString mString::substr(int start,int count){
    mString res;
    int i,k=start;
    res.st=new char[count+1];
    for (i=0;i<count;i++,k++){
        res.st[i]=st[k];
    }
    res.st[count+1]='\0';
    return res;
    
}
bool operator!=(const mString &s1,const mString &s2){
    bool pr = s1==s2;
    return !pr;
}
bool operator==(const mString &s1,const mString &s2){
    int i,k=0,k1=0,k2=0;
    while(s1.st[k1++]);
    k1--;
    while (s2.st[k2++]);
    k2--;
    if (k1!=k2) return 0;
    for (i=0;i<k1;i++) if (s1.st[i]!=s2.st[i]) return 0;
    return 1;
}
bool operator>=(const mString &s1,const mString &s2){
    bool pr =  (s1>s2) || (s1==s2);
    return pr;
}
bool operator>(const mString &s1,const mString &s2){
    int i,k=0,k1=0,k2=0;
    while(s1.st[k1++]);
    k1--;
    while (s2.st[k2++]);
    k2--;
    int l = k1;
    if (k2< l) l = k2;
    
    for (i=0;i<=k1;i++) {
        if (s1.st[i]>s2.st[i]) return 1;
        if (s1.st[i]<s2.st[i]) return 0;
    }
    return 0;
}
bool operator<=(const mString &s1, const mString &s2){
    bool pr = (s1>s2);
    return !pr;
}
bool operator<(const mString &s1, const mString &s2){
    bool pr = (s1>=s2);
    return !pr;
}
 

int mString::length(){
    if (!st) return 0;
    int k=0;
    while(st[k++]);
    return --k;
}
mString mString::replace(mString s1,mString s2){
    mString res;
    int start = 2;
    int count =2;
    int i,k=start;
    res.st=new char[count+1];
    for (i=0;i<count;i++,k++){
        res.st[i]=st[k];
    }
    res.st[count+1]='\0';
    return res;
}
int mString::find(mString &s){
    int k=s.length();
    char c = s.st[0];
    for (int i=0;i<length();i++)
        if (st[i]==c)
            if (s == substr(i,k))
                return i;
    return -1;
}
class Tpeep{
    protected:
    mString surname,name,otch,dr;
    int state;
    public:
    virtual void create(const mString &sur, const mString &na,const mString &ot,const mString &d){
        surname=sur;
        name=na;
        otch=ot;
        dr=d;
    }
    virtual void create(const char* sur,const char* na,const char* ot,const char* d){
        surname=sur;
        name=na;
        otch=ot;
        dr=d;
    }
    virtual void print()=0;
    int getState(){
        return state;
    }
    
};
class Tteacher: public Tpeep{
    public:
    mString predm[5];
    Tteacher(){
        state=1;
        for (int i=0;i<5;i++) predm[i]=0;
    }
    void print(){
        cout<<"Преподаватель"<<endl;
        cout<<surname<<" "<<name<<" "<<otch<<" "<<dr.substr(8,2)+"."+dr.substr(5,2)+"."+dr.substr(0,4)<<endl;
        cout<<"Дисциплина:";
        for (int i=0; i<5;i++) cout<<" "<<predm[i];
        cout<<endl;
    }
    void predmSet(int i, mString &vl){predm[i]=vl;}
    mString predmGet(int i){return predm[i];}
};
class Tstudent: public Tpeep{
    public:
    int marks[5];
    Tstudent(){
        state=0;
        for (int i=0;i<5;i++) marks[i]=0;
    }
    void print(){
        cout<<"Студент"<<endl;
        cout<<surname<<" "<<name<<" "<<otch<<" "<<dr.substr(8,2)+"."+dr.substr(5,2)+"."+dr.substr(0,4)<<endl;
        cout<<"Оценка:";
        for (int i=0; i<5;i++) cout<<" "<<marks[i];
        cout<<endl;
    }
    void markSet(int i, int vl){marks[i]=vl;}
    int markGet(int i){return marks[i];}
};
class builder2{
    public:
    void inputMarks(Tstudent* person){
        int i,o;
        cout<<"Введите оценки"<<endl;
        for (i=0;i<5;i++){
            cout<<"["<<i<<"]";cin>>o;
            person->markSet(i,o);
        }
    }
    void inputPredm(Tteacher* person){
        int i;
        mString o;
        cout<<"Введите дисциплину"<<endl;
        for (i=0;i<5;i++){
            cout<<"["<<i<<"]";cin>>o;
            person->predmSet(i,o);
        }
    }
};
class fabrika{
    public:
    Tpeep* create(const char* nm,const char* snm, const char* ot, const char* d, int type){
        mString nm1,snm1,ot1,d1;
        nm1=nm;
        snm1=snm;
        ot1=ot;
        d1=d;
        return create(nm1,snm1,ot1,d1,type);
    }
    Tpeep* create(mString &nm, mString &snm, mString &ot, mString &d, int type){
        Tpeep *res=NULL;
        if (type==0){
            res=new Tstudent;
            res->create(nm, snm,ot,d);
        }
        else if (type==1){
            res=new Tteacher;
            res->create(nm,snm,ot,d);
        }
        return res;
    }
};
int main()
{
    // cout<<"Hello World";
    // char c[100];
    
    //mString s,p,r;
    // s.test();
    // s="a3";
    // cout<<endl;
    // cout<< s<<endl;
    // // // r="asdasdfasdf123"+s;
    // // cout<<r<<endl;
    // // r=s+"asdasdfasdf123";
    // // cout<<r<<endl;
    // r=s.substr(1,4);
    // cout<<r;
    // s="133";
    // p="a3143";
    // bool pr=s<p;
    // cout<<pr<<endl;
    // // int pr = s.find(p);
    
    //s="123345";
    // mString s1;
    // s1 = '3';
    // mString s2 ;
    // s2 = "7";
    
    // p = s.replace(s1,s2);
    //p=s.substr(1,2);
    // cout<< s1;
    //cout<<p<<endl;
    
    // mString n,s,o,d;
    // s="Иванов";
    // n="Иван";
    // o="Иванович";
    // d="2000-11-12";
    
    // Tpeep* pers = new Tteacher;
    // pers->create(n,s,o,d);
    // pers->print();
    // Tpeep* stud = new Tstudent;
    // stud->create("Пётр","Петров","Петрович","2005-05-06");
    // stud->print();
    
    // fabrika dekanat;
    
    // Tpeep* pers1, *pers2;
    
    // pers1=dekanat.create(n,s,o,d,1);
    
    // pers2=dekanat.create("Семен", "Семионов", "Иоганович", "2000-04-01", 0);
    // pers1->print();
    // pers2->print();
    // delete pers1;delete pers2;
    
    // fabrika dekanat;
    // builder2 uchOtdel;
    // int k=1,t,i;
    // mString tmp;
    // Tpeep ** peeps=new Tpeep*[k];
    // for (i=0;i<k;i++){
    //     cout<<"Введите фамилию: " ;cin>>s;
    //     cout<<"Введите имя: ";cin>>n;
    //     cout<<"Введите отчество: ";cin>>o;
    //     cout<<"Введетие дату рождения: ";cin>>d;
    //     cout<<"Введите статус(0-судент,1-преподаватель): ";cin>>t;
    //     cin>>tmp;
    //     peeps[i]=dekanat.create(n,s,o,d,t);
    //     if (t==0){
    //         uchOtdel.inputMarks((Tstudent*)peeps[i]);
    //     }
    //     else if (t==1){
    //         uchOtdel.inputPredm((Tteacher*)peeps[i]);
    //     }
    // }
    // for (i=0;i<k;i++){
    //     if (peeps[i]->getState()==0)
    //         peeps[i]->print();
    // }
    return 0;
}
