#include <iostream>
#include <cmath>


using namespace std;

class point{
    private: 
    double x,y;
    public:
    point(){
        x=0;
        y=0;
    }
    point(double nx,double ny){
        //перегрузка конструктора
        x=nx;
        y=ny;
    }
    double getX(){
        return x;
    }
    double getY(){
        return y;
    }
    void setX(double nx){
        x=nx;
    }
    void setY(double ny){
        y=ny;
    }
    void printPoint(){
        cout<<"("<<x<<","<<y<<")";    
    }
};

class segment{
    private:
    point *P1,*P2;//динамическое использвоние одного класса в другом
    public:
    segment(){
        P1 = new point;
        P2 = new point;
    }
    segment(double x1,double y1,double x2,double y2){
        P1 = new point(x1,y1);
        P2 = new point(x2,y2);
    }
    ~segment(){//деструктов. обязательно разрушение используемых динамических объектов
        delete P1;
        delete P2;
    }   
    
    double length(){
        return sqrt(pow(P1->getX()-P2->getX(),2)+pow(P1->getY()-P2->getY(),2));
    }
    point * getFirstPoint(){//результаттом функции является указатель на объект типа point
        point *tmp = new point(P1->getX(),P1->getY());
        return tmp;
    }
    point * getSecondPoint(){
        point *tmp = new point(P2->getX(),P2->getY());
        return tmp;
    }   
    
    void print(){//печать координат начала и конца отрезка
        cout<<"[";
        P1->printPoint();
        cout<<",";
        P2->printPoint();
        cout<<"]";
    }
    
    //point * getMeedle(){//реализовать метод получения точки, которая является серединой отрезка
    //    cout<<"("<<(P1->getX()+P2->getX())/2<<","<<(P1->getY()+P2->getY())/2<<")";
    //}
    
    bool pointOnLine(point *P){//возвращает true если точка P лежит на прямой, на которой лежит отрезок
        double m,n,m1,n1;
        m=P1->getX()-P2->getX();
        n=P1->getY()-P2->getY();
        m1=P1->getX()-P->getX();
        n1=P1->getY()-P->getY();
        return (m/m1)==(n/n1);
    }
    
    bool pointBelongs(point *P){//возвращает true если точка P принадлежит отрезоку
        if(!pointOnLine(P))
            return 0;
        if (((P1->getX()>=P->getX()&&P->getX()>=P2->getX())||(P1->getX()<=P->getX()&&P->getX()<=P2->getX()))&&((P1->getY()>=P->getY()&&P->getY()>=P2->getY())||(P1->getY()<=P->getY()&&P->getY()<=P2->getY()))) return 1;
        return 0;
    
        
    }

    
};
class figure{
    private:
    point *pi;
    int dl;
    public:
    figure(){
        pi=NULL;
    }
    figure(int n){
        dl=n;
        pi = new point[n];
        double x,y;
        for(int i=0;i<n;i++){
            cin>>x;
            cin>>y;
            pi[i]=point(x,y);
        }
    }
    ~figure(){//деструктов. обязательно разрушение используемых динамических объектов
        delete pi;
    }
    void print(){
        for(int i=0;i<dl;i++){
            pi[i].printPoint();
        }
    }
    double length(){
        double l;
        for(int i=0;i<dl-1;i++){
            l+=sqrt(pow(pi[i].getX()-pi[i+1].getX(),2)+pow(pi[i].getY()-pi[i+1].getY(),2));
        }
        return l;
    }
    double Striangle(){
        float res;
        res=0.5*abs((pi[1].getX()-pi[0].getX())*(pi[2].getY()-pi[0].getY())-(pi[2].getX()-pi[0].getX())*(pi[1].getY()-pi[0].getY()));
        return res;
    }
    double Smnog(){
        double res=0.0;
        for(unsigned i=0,j=1;i<dl;j=(++i+1)%dl){
            res+=(pi[j].getX()-pi[i].getX())*(pi[j].getY()+pi[i].getY());
        }
        return fabs(0.5*res);
    }
    double Prov(){
        int i,j,k;
        int flag = 0;
        double z;
        if (dl < 3)
            return(0);
        for (i=0;i<dl;i++) {
            j = (i + 1) % dl;
            k = (i + 2) % dl;
            z  = (pi[j].getX() - pi[i].getX()) * (pi[k].getY() - pi[j].getY());
            z -= (pi[j].getY() - pi[i].getY()) * (pi[k].getX() - pi[j].getX());
            if (z < 0)
                flag |= 1;
            else if (z > 0)
                flag |= 2;
            if (flag == 3)
                return false;//Не выпуклая
        }
        if (flag != 0)
            return true; //Выпуклая
        else
            return 0;
    }
};
int main()
{
    /*point P;
    //P.printPoint();
    point P2(3,5);
    //P2.printPoint();
    cout << endl;
    segment *AB = new segment(3,-5,-1,1);
    cout << AB->length();
    cout << endl;
    
    //point *AB1 = AB->getFirstPoint();
    //point *AB2 = AB->getSecondPoint();
    //AB1->printPoint();
    //cout << endl;
    //AB2->printPoint();
    //cout<<endl;
    AB->print();
    cout<<endl;
    //AB->getMeedle();
    //cout<<endl;
    cout<<AB->pointBelongs(&P2);*/
    figure g;
    figure h(4);
    /*h.print();
    cout<< h.length();*/
    /*cout<<h.Striangle();*/
    /*cout<<h.Smnog();*/
    cout<<h.Prov();
    return 0;
}
