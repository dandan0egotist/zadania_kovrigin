#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

class MyArray{
    private:
    int n, *ms;

    public:
    MyArray(){
        n=0;
        ms=NULL;
        //cout « "constructor\n";
    }
    ~MyArray(){
        if(ms) delete ms;
        // cout « "destructor\n";
    }
    void init(int k){
        if(ms) delete ms;
        ms = new int[k];
        n=k;
        for (int i=0;i<n;i++) ms[i]=0;
    }
    void print(){
        for (int i=0;i<n;i++) cout<<ms[i]<<" ";
        cout << endl;
    }
    void set(int k, int v){
        ms[k]=v;
    }
    int get(int k){
        return ms[k];
    }
    void random(int left, int right){
        srand(time(0));
        for (int i=0;i<n;i++) ms[i]=rand()%(right-left)+left;
    }
    int length(){
        return n;
    }

    void removeElm(int r){
        int i,t,n1=n;
        for(i=0;i<n;i++)if (ms[i]==r)n1--;
        int *tmp=new int[n1];
        t=0;
        for(i=0;i<n;i++)if (ms[i]!=r)tmp[t++]=ms[i];
        delete ms;
        ms=tmp;
        n=n1;
    }
    void max(){
        int i,t=ms[0];
        for(i=1;i<n;i++)if (ms[i]>t)t=ms[i];
        cout<<t<<endl;
    }
    void min(){
        int i,t=ms[0];
        for(i=1;i<n;i++)if (ms[i]<t)t=ms[i];
        cout<<t<<endl;
    }
    void sum(){
        int i,t=ms[0];
        for(i=1;i<n;i++)t+=ms[i];
        cout<<t<<endl;
    }
    void proiz(){
        int i,t=ms[0];
        for(i=1;i<n;i++)t*=ms[i];
        cout<<t<<endl;
    }
    void srsum(){
        int i,t=ms[0];
        for(i=1;i<n;i++)t+=ms[i];
        t/=n;
        cout<<t<<endl;
    }
    void srproiz(){
        int i,t=ms[0];
        for(i=1;i<n;i++)t*=ms[i];
        t/=n;
        cout<<t<<endl;
    }
    void ub(){
        int i,t=ms[0],k=0;
        for(i=1;i<n;i++){
            if (ms[i]>=t){
                k=1;
                t=ms[i];
            }        
        }
        if (k==1)cout<<"Нет убывания"<<endl;
        else cout<<"Есть убывание"<<endl;
    }
    void voz(){
        int i,t=ms[0],k=0;
        for(i=1;i<n;i++){
            if (ms[i]<=t){
                k=1;
                t=ms[i];
            }        
        }
        if (k==1)cout<<"Нет возрастания"<<endl;
        else cout<<"Есть возрастание"<<endl;
    }
    void sort1(){
        int n1=n,t;
	    while(n1--){
		    bool t=false;
		    for(int i=1; i<n;i++){
			    if (ms[i-1]>ms[i]){
				    swap(ms[i-1], ms[i]);
				    t = true;
			    }
		    }
		    if (t==false)
		        break;
	    }
    }
    void sort2(){
        int k;
	    for(int i=1;i<n;i++){
		    k=i-1;
		    while(k>=0 && ms[k]>ms[k+1]){
			    swap(ms[k], ms[k+1]);
			    k--;
		    }
	    }
    }
    };

int main()
{
    // MyArray m;
    // m.init(10);
    // m.print();

    MyArray *a;
    int k;
    a= new MyArray;

    cin >>k;
    a->init(k);
    int s,d;

    // a->set(0,s);
    // for (int i=1;i<k;i++){
    //      a->set(i,a->get(i-1)+d);
    // }

    a->random(10,15);

    // int cnt=0;
    // for (int i=1;i<a->length()-1;i++){
    //      if (a->get(i)>a->get(i-1) && a->get(i)>a->get(i+1)) cnt++;
    // }

    a->print();
    //a->max();
    //a->min();
    //a->sum();
    //a->proiz();
    //a->srsum();
    //a->srproiz();
    //a->ub();
    //a->voz();
    a->sort1();
    a->print();
    a->sort2();
    a->print();
    //cin>>s;
    //a->removeElm(s);

    //a->print();

    // cout « cnt« endl;
    cout <<"work\n";
    
    delete a;
    return 0;
}
