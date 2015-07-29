//# Uva_Happy_Number

#include <iostream>
#include <cstdio>
#include <cmath>
#include <vector>
#include <list>
#include <algorithm>
#define LL long long
#define sf scanf
using namespace std;

int main ()
{
    long s,n,a,b,x,y,t,m,p,tc;
    vector <long> v;
    scanf ("%ld",&tc);

    for (t=1;t<=tc;t++){
    {
        scanf ("%ld",&n);
        s=0;

        if (n > 9)
        {
            a=n;
            b=n;
            do
            {
                a=a%10;
                v.push_back(a);
                b=b/10;
                //swap(a,b);
                a=b;
            }while(b>=10);
            v.push_back(a);
        }

        else
        {
            //a = (n*n);
            v.push_back(n);
        }

        for (int i=0;i<v.size();i++)
        {
            //cout <<v[i] << " ";
            s+=(v[i]*v[i]);
        }

        //cout << s << " " <<t << endl;
        v.clear();

        if (s>9)
        {
            a=s;
            b=s;
            do
            {
                a=a%10;
                v.push_back(a);
                b=b/10;
                //swap(a,b);
                a=b;

                if (a == 0)
                {
                    s=0;
                    for (int i=0;i<v.size();i++)
                    {
                        s+=(v[i]*v[i]);
                    }
                    //cout << s << endl;
                    v.clear();
                    a=s;
                    b=s;
                }

            }while(s>=10);
        }

        //cout << s << endl;

        if (s==1)
        {
            printf("Case #%ld: %ld is a Happy number.\n",t,n);
        }

        else
        {
            printf("Case #%ld: %ld is an Unhappy number.\n",t,n);
        }
        v.clear();
    }
    }

    return 0;
}

