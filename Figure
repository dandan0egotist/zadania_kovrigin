#include <iostream>
#include <cmath>

using namespace std;

class figure{
    protected:
    double x,y;
    public:
    figure(){
        x=0;
        y=0;
    }
    figure(double nx, double ny){
        x=nx;
        y=ny;
    }
    void virtual print(){
        cout << "("<<x<<","<<y<<")";
    }
    double virtual area()=0;
    double virtual lenth()=0;
};
class circle : public figure {
    protected:
    double r;
    public:
    circle (double nx, double ny, double nr){
        x=nx;y=ny;r=nr;
    }
    double area(){
        return r*r*4*atan(1);
    }
    double lenth(){
        return 2*r*4*atan(1);
    }
};
class square : public figure{
    protected:
    double f;
    public:
    square (double nx, double ny, double nf){
        x=nx;y=ny;f=nf;
    }
    double area(){
        return f*f*4;
    }
    double lenth(){
        return 4*f;
    }
    void print(){
        cout<<"("<<x<<","<<y<<"),"<<"("<<x+f<<","<<y<<")"<<","<<"("<<x<<","<<y-f<<")"<<","<<"("<<x+f<<","<<y-f<<")";
    }
};
class triangle : public figure{
    protected:
    double x1,x2,x3,y1,y2,y3;
    public:
    triangle (double nx1, double ny1, double nx2, double ny2, double nx3, double ny3){
        x1=nx1;x2=nx2;x3=nx3;y1=ny1;y2=ny2;y3=ny3;
    }
    double area(){
        double AB1=x2-x1;
        double AB2=x3-x1;
        double AC1=y2-y1;
        double AC2=y3-y1;
        return abs(0.5*(AB1*AC2-AB2*AC1));
    }
    double lenth(){
        return 0;
    }
    void print(){
        cout<<"("<<x1<<","<<y1<<"), ("<<x2<<","<<y2<<"), ("<<x3<<","<<y3<<")";
    }
};

int main()
{
    figure *p;
    // circle *c;
    // p=new figure(2,3);
    // p->print();
    //cout<<endl;
    // p=new circle(1,1,1);
    // p->print();
    // cout<<endl;
    // cout<<p->area()<<" "<<p->lenth()<<endl;
    // p=new square(5,6,3);
    // p->print();
    // cout<<endl;
    // cout<<p->area()<<" "<<p->lenth()<<endl;
    p=new triangle(1,2,3,4,5,6);
    cout<<endl;
    p->print();
    cout<<endl;
    cout<<p->area()<<endl;
    return 0;
}
