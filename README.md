# sum-of-a-integer-with-a-two-prime-numbers
#include <iostream>
using namespace std;

float checkPrime(int n);

int main() 
{
    int n, i;
    float y = false;

    cout << "Enter a positive  integer: ";
    cin >> n;

    for(i = 2; i <= n/2; ++i) 
	{
        if (checkPrime(i)) 
		{
            if (checkPrime(n - i)) 
			{
                cout << n << " = " << i << " + " << n-i << endl;
                y = true;
            }
        }
    }

    if (!y)
      cout << n << " can't be expressed as sum of two prime numbers.";

    return 0;
}

float checkPrime(int n)
{
    int i;
    float isPrime = true;

    if (n == 0 || n == 1) 
	{
        isPrime = false;
    }
    else 
	{
        for(i = 2; i <= n/2; ++i) 
		{
            if(n % i == 0) 
			{
                isPrime = false;
                break;
            }
        }
    }

    return isPrime;
}
  
  
  
  output:
  Enter a positive  integer: 34
34 = 3 + 31
34 = 5 + 29
34 = 11 + 23
34 = 17 + 17
