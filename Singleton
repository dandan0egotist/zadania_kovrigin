#include <iostream>

using namespace std;
class Singleton
{
    private:
    int val;
    Singleton() {val=0;}
    Singleton( const Singleton&);
    Singleton& operator=(Singleton&);
    public:
    int getval(){
        return val;
    }
    void setval(int v){
        val=v;
    }
    
    static Singleton& getInstance(){
        static Singleton instance;
        return instance;
    }
    
};
int main()
{
  Singleton& s = Singleton::getInstance();
  Singleton& p = Singleton::getInstance();
  cout<<s.getval()<< " " << p.getval()<< endl;
  s.setval(4);
  cout<<s.getval()<< " " << p.getval()<< endl;
  p.setval(6);
  cout<<s.getval()<< " " << p.getval()<< endl;

    return 0;
}
