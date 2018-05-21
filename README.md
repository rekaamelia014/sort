/*program pengurutan data dengan cara Buble Sort, Selection Sort, Merge Sort*/


#include <iostream>
using namespace std;
void merge(int data[], int l, int m, int r)
{

    int k1 = m - l + 1;
    int k2 =  r - m;
    int i,j,k;
    int kiri[k1];
    int kanan[k2];

    for (int i = 0; i < k1; i++)
        kiri[i] = data[l + i];
    for (int j = 0; j < k2; j++)
        kanan[j] = data[m + 1+ j];

    i = 0;
    j = 0;
    k = l;
    while (i < k1 && j < k2)
    {
        if (kiri[i] <= kanan[j])
        {
            data[k] = kiri[i];
            i++;
        }
        else
        {
           data[k] = kanan[j];
            j++;
        }
        k++;
    }
    while (i < k1)
