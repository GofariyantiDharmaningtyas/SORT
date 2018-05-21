// DESRIZAL DWI AYU 17170510
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
