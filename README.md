#include<iostream>
using namespace std;
int GetMax(int a, int b)   //得到两个数的最大值
{
    return (a) > (b) ? (a) : (b);
}

int GetMaxAddOfArray(int* arr, int sz)
{
    if (arr == NULL || sz <= 0)
        return 0;

    int Sum = arr[0];   //临时最大值
    int MAX = arr[0];   //比较之后的最大值

    for (int i = 1; i < sz; i++)
    {
        Sum = GetMax(Sum + arr[i], arr[i]);   //状态方程

        if (Sum >= MAX)
            MAX = Sum;
    }
    return MAX;
}

int main()
{
    int n;
    cin >> n;
    int array[100] = {0};
    for (int i = 0; i < n; i++)
    {
        cin >> array[i];
    }
    
    int sz = sizeof(array) / sizeof(array[0]);
    int MAX = GetMaxAddOfArray(array, sz);
    cout << MAX << endl;
    return 0;
}
