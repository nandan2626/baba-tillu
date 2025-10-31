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

