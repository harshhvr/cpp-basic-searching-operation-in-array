# Searching Operation in C++

Basic searching operation on array in C++

## Table of Contents

  - [Linear Search](#linear-search)
  - [Binary Search](#binary-search)

## Linear Search

[Open](./linearsearch.cpp) file to view the code.

**Time Complexity:** O(n)

**Code**

```
#include <iostream>
using namespace std;

int linearSearch(int arr[], int n, int key)
{
    for (int i = 0; i < n; i++)
    {
        if (arr[i] == key)
        {
            return i;
        }
    }
    return -1;
}

int main()
{
    int n;
    cin >> n;

    int arr[n];
    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }

    int key;
    cin >> key;

    cout << linearSearch(arr, n, key);

    return 0;
}
```

**Output**

```
5
10 20 37 45 60
37
2
```

## Binary Search

[Open](./binarysearch.cpp) file to view the code.

**Time Complexity:** O(log<sub>2</sub> n)

**Code**

```
#include <iostream>
using namespace std;

int binarySearch(int arr[], int n, int key)
{
    int s = 0;
    int e = n;

    while (s <= e)
    {
        int mid = (s + e) / 2;

        if (arr[mid] == key)
        {
            return mid;
        }
        else if (arr[mid] > key)
        {
            e = mid - 1;
        }
        else
        {
            s = mid + 1;
        }
    }
    return -1;
}

int main()
{
    int n;
    cin >> n;

    int arr[n];
    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }

    int key;
    cin >> key;

    cout << binarySearch(arr, n, key);

    return 0;
}
```

**Output**

```
5
45 60 78 14 32
14
3
```