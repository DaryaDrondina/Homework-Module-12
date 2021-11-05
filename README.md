#include <iostream>
#include <clocale>

using namespace std;

    bool isPrefix(string str,int length,int i,int k) 
    {
    if (i + k > length)
    return false;
    for (int j = 0; j < k; j++)
    {
    if (str[i] != str[j])
    return false;
    i++;
    }
    return true;
    }

    bool isKPeriodic(string str,int length,int k)
    {
    for (int i = k; i < length; i += k)
    if (!isPrefix(str, length, i, k))
    return false;
    return true;
    }

    int main()
    {
        setlocale(LC_ALL, "Russian");
    string str = "abcabcabcabc";
    int length = str.length();
    int k = 3;
    if (isKPeriodic(str, length, k))
    cout << ("Строка кратная");
    else cout << ("Строка некратна");
    }