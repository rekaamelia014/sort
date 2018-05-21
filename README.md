/*program pengurutan data dengan cara Buble Sort, Selection Sort, Merge Sort*/
/* Noverina Ika Tama - 1717051005, Naurah Nadzifah - 1717051032, Reka Amelia - 1717051046, Reda Meiningtiyas - 1717051055*/

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
        {
        data[k] = kiri[i];
        i++;
        k++;
    }
    while (j < k2)
    {
        data[k] = kanan[j];
        j++;
        k++;
    }
}

void mergeSort(int data[], int l, int r)
{
    if (l < r)
    {

        int m = l+(r-l)/2;
        mergeSort(data, l, m);
        mergeSort(data, m+1, r);
        merge(data, l, m, r);
    }
}

void printArray(int A[], int size)
{
    int i;
    for (i=0; i < 8; i++)
        cout<<A[i]<<" ";
cout<<endl;
}

int main (){
int pilihan;
int a,b,c,n,i,j,k,m,r,k1,k2,temp;
int x[100];
int data [100];

cout<<"Pilihan Sorting"<<endl;
cout<<"1. Selection Sort"<<endl;
cout<<"2. Bubble Sort"<<endl;
cout<<"3. Merge Sort"<<endl;
cout<<"masukkan pilihan :";
cin>>pilihan;

switch(pilihan){
case 1:
    cout<<"input banyaknya data : ";
	cin>>n;
	cout<<" sebelum di urutkan :"<<endl;
	 for(i=0;i<n;i++){
	 	cin>>x[i];
	 }
	 for(i=0;i<n-1;i++){
		a=x[i];
		b=i;
			for (j=i+1;j<n;j++){
				if (a>x[j]){
					a=x[j];
					b=j;
				}
			}
			c=x[i];
        x[i]=x[b];
        x[b]=c;
    }
    cout<<"sesudah di urutkan : ";
	for(i=0;i<n;i++)
    {
        cout<<x[i];
		cout<<" ";
    }
    break;
case 2:
    cout<<"Masukkan banyak data : ";
cin>>n;
cout<<"Masukkan data : "<<endl;
	for(i=0;i<n;i++)
	cin>>data[i];

for(i=0;i<n;i++)
	{
		for(j=0;j<(n-1);j++)
			if(data[j]>data[j+1])
		 {
		 		temp=data[j];
		 		data[j]=data[j+1];
		 		data[j+1]=temp;

		 }
	}

cout<<"Nilai urutan data : ";
	for(i=0;i<n;i++)
	cout<<" "<<data[i];
break;
case 3:

    int data[8] ={12, 8, 5, 28, 6, 10, 9, 13};
    cout<<"data ter-input adalah..."<<endl;
    for (int i=0 ; i<=7 ; i++) {
        cout<< data[i]<<" ";
    }
mergeSort(data, 0, 8-1);
    cout<<endl;
    cout<<"Data telah diurutkan \n"<<endl;
    printArray(data, 8);
break;
}
return 0;
}

