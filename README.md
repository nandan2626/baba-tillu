1. Program to Evaluate the Expression X = (-b ± √(b² - 4ac)) / 2a







#include <iostream>
#include <cmath>
using namespace std;
int main() {
double a, b, c, x1, x2;
cout << "Enter values for a, b, and c: ";
cin >> a >> b >> c;
double discriminant = b * b - 4 * a * c;
if (discriminant >= 0) {
x1 = (-b + sqrt(discriminant)) / (2 * a);
x2 = (-b - sqrt(discriminant)) / (2 * a);
cout << "Roots are: " << x1 << " and " << x2 << endl;
} else {
cout << "Roots are imaginary." << endl;
}
return 0;
}

2. Program for Class "Staff" to Calculate Gross Salary
#include <iostream>
using namespace std;
class Staff {
public:
string name;
double basic, DA, HRA, gross_salary;
void input() {
cout << "Enter name: ";
cin >> name;
cout << "Enter basic salary: ";
cin >> basic;
}
void calculate() {
DA = 0.745 * basic;
HRA = 0.3 * basic;
gross_salary = basic + DA + HRA;
}
void display() {
cout << "Name: " << name << "\nGross Salary: " << gross_salary << endl;
}
};
int main() {
Staff staff;
staff.input();
staff.calculate();
staff.display();
return 0;
}

3. Program for Two Classes Using Friend Function to Calculate Average Marks
#include <iostream>
using namespace std;
class Test2;
class Test1 {
int marks1;
public:
void input() {
cout << "Enter marks for Test1: ";
cin >> marks1;
}
friend float average(Test1, Test2);
};
class Test2 {
int marks2;
public:
void input() {
cout << "Enter marks for Test2: ";
cin >> marks2;
}
friend float average(Test1, Test2);
};
float average(Test1 t1, Test2 t2) {
return (t1.marks1 + t2.marks2) / 2.0;
}
int main() {
Test1 t1;
Test2 t2;
t1.input();
t2.input();
cout << "Average Marks: " << average(t1, t2) << endl;
return 0;
}

4. Program for Class "Account" with Filter for Balance Greater Than 10,000
#include <iostream>
using namespace std;
class Account {
public:
int account_no;
double balance;
void input() {
cout << "Enter Account Number: ";
cin >> account_no;
cout << "Enter Balance: ";
cin >> balance;
}
void display() {
if (balance > 10000) {
cout << "Account No: " << account_no << " | Balance: " << balance << endl;
}
}
};
int main() {
Account accounts[10];
for (int i = 0; i < 10; i++) {
accounts[i].input();
}
cout << "Accounts with Balance > 10000:\n";
for (int i = 0; i < 10; i++) {
accounts[i].display();
}
return 0;
}

5. Program for Class "Student" with Constructor to Initialize Data
#include <iostream>
using namespace std;
class Student {
string name;
float percentage;
public:
Student(string n, float p) : name(n), percentage(p) {}
void display() {
cout << "Name: " << name << "\nPercentage: " << percentage << "%" << endl;
}
};
int main() {
string name;
float percentage;
cout << "Enter name: ";
cin >> name;
cout << "Enter percentage: ";
cin >> percentage;
Student student(name, percentage);
student.display();
return 0;
}

6. Program for Class "Polygon" with Derived Classes "Rectangle" and "Triangle"
#include <iostream>
using namespace std;
class Polygon {
protected:
double width, height;
public:
void set_values(double w, double h) {
width = w;
height = h;
}
virtual double area() = 0;
};
class Rectangle : public Polygon {
public:
double area() override {
return width * height;
}
};
class Triangle : public Polygon {
public:
double area() override {
return (width * height) / 2;
}
};
int main() {
Polygon* poly;
Rectangle rect;
Triangle tri;
rect.set_values(5, 3);
tri.set_values(5, 3);
poly = &rect;
cout << "Rectangle area: " << poly->area() << endl;
poly = &tri;
cout << "Triangle area: " << poly->area() << endl;
return 0;
}

7. Program to Copy Contents from One File to Another
#include <iostream>
#include <fstream>
using namespace std;
int main() {
ifstream infile("source.txt");
ofstream outfile("destination.txt");
if (!infile || !outfile) {
cout << "Error opening files!" << endl;
return 1;
}
char ch;
while (infile.get(ch)) {
outfile.put(ch);
}
cout << "File copied successfully!" << endl;
infile.close();
outfile.close();
return 0;
}
