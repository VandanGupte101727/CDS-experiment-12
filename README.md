# CDS-experiment-12

AIM:- To study and implement constructors and destructors<br>

Software Used:- VS code <br>

Theory:-<br>
A constructor is a member function of a class that is automatically invoked when an object of the class is created. It ensures proper initialization of the object’s data members and resources.<br>

Types of Constructors:<br>
1).Default Constructor: Takes no arguments or has default parameters. If no constructor is defined, the compiler provides a default constructor.<br>
2).Parameterized Constructor: Allows passing arguments to initialize the object with specific values.<br>
3).Copy Constructor: Used to create a new object as a copy of an existing object. If not explicitly defined, the compiler generates a default one that performs a shallow copy.<br>

Destructors: In C++, a destructor is a special member function that is automatically called when an object goes out of scope or is explicitly deleted. Its main purpose is to release resources (like memory or file handles) acquired during the object's lifetime, ensuring proper cleanup. A destructor has the same name as the class, prefixed with a tilde (~), and cannot be overloaded. It plays a crucial role in avoiding resource leaks and is integral to RAII (Resource Acquisition Is Initialization).<br>


CODE:-

1).<br>

    #include <iostream>
    using namespace std;

    class student {
    int rn;
    char n[50];
    float avg;
    public:
    student() {
        cout << "Enter the name: ";
        cin >> n;
        cout << "Enter the roll no.: ";
        cin >> rn;
        cout << "Enter the average: ";
        cin >> avg;
    }

    void display() {
        cout << endl;
        cout << "Name: " << n << endl;
        cout << "Roll No: " << rn << endl;
        cout << "Average: " << avg << "%" << endl;
    }
    };

    int main() {
    student s1;
    s1.display();
    return 0;
    }

2).<br>
    
    #include <iostream>
    using namespace std;

    class student
    {
    int rn;
    char n[50];
    float avg;
    public:
    student();
    void display();
    };
    student::student()
    {
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
    }
    void student::display()
    {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<endl;
    }
    int main()
    {
    student s1;
    s1.display();
    return 0;
    }

3).<br>

    #include <iostream>
    using namespace std;

    //default constructor
    class student
    {
    int rn;
    char n[50];
    double m1, m2, m3;
    public:
    student()
    {
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the subject 1 marks: ";
    cin>>m1;
    cout<<"Enter the subject 2 marks: ";
    cin>>m2;
    cout<<"Enter the subject 3 marks: ";
    cin>>m3;
    }

    void display()
    {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Marks for subject 1: "<<m1<<endl;
    cout<<"Marks for subject 2: "<<m2<<endl;
    cout<<"Marks for subject 3: "<<m3<<endl;
    }
    };
    int main()
    {
    student s1;
    s1.display();
    return 0;
    }

4).<br>

    #include <iostream>
    using namespace std;

    //types of constructor - parameterized constructor
    class maxop
    {
    public:
    maxop(int a, int b)
    {
    cout<<"First Number: "<<a<<endl;
    cout<<"Second Number: "<<b<<endl;
    cout<<endl;
    if (a>b)
    {
        cout<<"The first number is greater than the second.";
    }
    else if (b>a)
    {
        cout<<"The second number is greater than the first. ";
    }
    else
    {
        cout<<"Both numbers are equal. ";
    }
    }
    };

    int main()
    {
    maxop n1(23,76);
    }

4).<br>

    #include<iostream>
    #include<string.h>
    using namespace std;

    //copy constructor
    class student
    {
    int rn;
    char n[50];
    float avg = 0;
    public:
    student(int,char[],float);

    student(student &t)
    {
        rn=t.rn;
        strcpy(n,t.n);
        avg=t.avg;
    }
    void display();

    };

    student::student(int rno,char na[],float av)
    {
    rn=rno;
    strcpy(n,na);
    avg=av;
    }

    void student::display()
    {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<" %"<<endl;
    }

    int main()
    {
    student s1(36,"vandan",93.7);
    s1.display();

    student vandan(s1);
    vandan.display();

    return 0;
    }
    
