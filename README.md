#include <iostream>
using namespace std;

void swap(int arr[],int i,int j)
{
    int t=arr[i];
    arr[i]=arr[j];
    arr[j]=t;
}

int partition(int arr[],int low,int high)
{
    
    int i= low-1;
    for (int j=low;j<high;j++)
    {
        if (arr[j]<arr[high])
        {
            i++;
            swap(arr,i,j);
        }
        
    }
    swap(arr,i+1,high);
    return i+1 ;
}


void quicksort(int arr[] ,int low ,int high)
{
    
    if (low<high)
    {
        int pi= partition(arr,low,high);
        quicksort(arr,low,pi-1);
        quicksort(arr,pi+1,high);
        
    } 
    
    
}


int main()
{
	// your code goes here
    int arr[5]={56,499,3,2,11};
    quicksort(arr,0,4);
    for (int i=0;i<5;i++){
        cout<< arr[i]<<" ";
    }cout<<endl;
        
	return 0;
}
