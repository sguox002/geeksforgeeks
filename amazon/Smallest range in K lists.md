### Problem Summary
Given k sorted list, find smallest range including at least one element from each list

### idea
using merge sort and find the min/max for all current values. This naive solution will TLE
Better approach: using minheap to push and pop and we no need to sort et al. In this case a proper data structure is important.

### code
naive approach

```cpp
void findSmallestRange(int arr[][N], int n, int k)
{
      //code here
      vector<int> pt(k);
      int maxInd=0;
      int min0,max0,min_range=INT_MAX;
      int themin,themax;
      while(maxInd<n)
      {
          max0=min0=arr[0][pt[0]];
          vector<int> vt(k);
          for(int i=0;i<k;i++) vt[i]=arr[i][pt[i]];
          int min_ind=min_element(vt.begin(),vt.end())-vt.begin();
          int max_ind=max_element(vt.begin(),vt.end())-vt.begin();
          if(vt[max_ind]-vt[min_ind]<min_range)
          {
              themin=vt[min_ind],themax=vt[max_ind];
              min_range=themax-themin;
          }
          pt[min_ind]++;
          maxInd=max(maxInd,pt[min_ind]);
      }
      cout<<themin<<" "<<themax<<endl;
}
```
