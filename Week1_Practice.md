
# Week 1
Hey guys! This is my first week of practice:)

## 1.Sieve of Eratosthenes:
This algorithm is used to find all prime numbers below a given number.
Its time complexity is O(n*log(log(n))).

[Reading](https://www.geeksforgeeks.org/sieve-of-eratosthenes/?ref=lbp)

[Video](https://youtu.be/T8PaMnb0GPo?si=YvYk8MXK8DKNG7eq)

## Code
```cpp
#include<bits/stdc++.h>
using namespace std;

void Sieve(int n){
    bool Prime[n+1]; //declare an array to store values from 0 to n
    memset(Prime,true,sizeof(Prime));//set all values to true
    for(int p=2;p*p<=n;p++){//there should be a factor less that sqrt(n)
        if(Prime[p]){//check if prime
            for(int i=p*p;i<=n;i+=p){//if so set all its multiple as false
                Prime[i]=false;
            }
        }
    }
    for(int p=2;p<=n;p++){
        if(Prime[p])
            cout<<p<<" ";
    }
}

int main(){
    Sieve(50);
    return 0;
}
```

## 2.GCD and LCM using Euclid's Algorithm:
Using Euclidean algorithm to compute GCD and LCM of given numbers.
Its time complexity is O(log(min(a,b))).

[Reading](https://www.geeksforgeeks.org/java-program-to-find-gcd-and-lcm-of-two-numbers-using-euclids-algorithm/)

[Video](https://youtu.be/yHwneN6zJmU?si=OYrmSmMNb1Sfeewe)

## Code
```cpp
#include<bits/stdc++.h>
using namespace std;

int GCD(int a, int b){
    if(a==0||b==0){
        int x;
        return x=a>b?a:b;
    }
    if(a>b){
        GCD(a%b,b);
    }
    else{
        GCD(a,b%a);
    }

}

int LCM(int a, int b){
    return a*b/GCD(a,b);
}

int main(){
    cout<<GCD(75,50)<<endl;
    cout<<LCM(50,75)<<endl;
    return 0;
}
```
