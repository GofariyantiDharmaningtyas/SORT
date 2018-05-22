// DESRIZAL DWI AYU 1717051019
// ALIFIA INTAN A.N. 1717051028
// GOFARIYANTI DHARMANINGTYAS 1717051048
// TARI TRINATHA 1717051058

#include <iostream>
using namespace std;

int bubble(){
	bool sorted;
	int n, tmp;
	cout<<"Banyaknya bilangan yang akan diurutkan = ";
	cin>>n;
	int bil[n];
	for(int i=0;i<n;i++){
		cout<<"Bil "<<i+1<<" = ";
		cin>>bil[i];
	}
	cout<<"Nilai yang akan diurutkan\n";
	for(int i=0;i<n;i++){
		cout<<bil[i]<<" ";
	}
	for(int g=0;g<n;g++){
		sorted=false;
		for(int h=0;h<n;h++){
			for(int i=0;i<n-1;i++){
				if(bil[i]>bil[i+1]){
					tmp=bil[i];
					bil[i]=bil[i+1];
					bil[i+1]=tmp;
					sorted=true;
				}
			}
		}
		if(!sorted){
			break;
		}
	}
	cout<<"\nHasil bubble sort\n";
	for(int i=0;i<n;i++){
		cout<<bil[i]<<" ";
	}
	return 0;
}
int select(){
	int n,i,j,imaks,tmp,L[10];
	cout<<"Banyak elemen: ";
    cin>>n;
    cout<<"Masukkan elemen: \n";
    for(i=0;i<n;i++)
    {
        cin>>L[i];
    }
	for(int i=10-1;i>0;i--){
		imaks=0;
		for(int j=1;j<=i;j++){
			if (L[j]<L[imaks]){
			imaks=j;
		}
	}
	tmp=L[imaks];
	L[imaks]=L[i];
	L[i]=tmp;
}	
cout<<"Hasil selection sort: ";
 for(int i=0; i<n; i++)
 {
  cout<<" "<<L[i];
 }
 return 0;
}
void merge(int *a, int low, int high, int mid){
	int i,j,k,tmp[high-low+1];
	i=low;
	j=mid+1;
	k=0;
	while (i<=mid && j<=high){
		if (a[i]<a[j]){
			tmp[k]=a[i];
			k++;
			i++;
		}
		else{
			tmp[k]=a[j];
			k++;
			j++;
		}
	}
	while (i <= mid){
		tmp[k] = a[i];
		k++;
		i++;
	}
	while (j <= high){
		tmp[k] = a[j];
		k++;
		j++;
	}
	for (i=low; i<=high; i++){
		a[i] = tmp[i-low];
	}
}
 
void sort(int *a, int low, int high){
	int mid;
	if (low<high){
		mid=(low+high)/2;
		sort(a,low,mid);
		sort(a,mid+1,high);
		merge(a,low,high,mid);
	}
}
int mergee(){
	int n;
	cout<<"Banyak Integer :";
	cin>>n;
	int bil[n];
	for(int i=0; i<n; i++){
		cout<<"Bil ke-"<<i+1<<"= ";
		cin>>bil[i];
	}
	sort(bil, 0, n-1);
	cout<<"\nHasil :\n";
	for (int i=0; i<n; i++){
        cout<<"  "<<bil[i];
    }
	return 0;
}

int main(){
	int menu;
	cout<<"1. Bubble Sort\n2. Selection Sort\n3. Merge Sort\n Pilih 1/2/3 . . . ";
	cin>>menu;
	switch(menu){
		case 1:
			bubble();
			break;
		case 2:
			select();
			break;
		case 3:
			mergee();
			break;
		}
	return 0;
}
