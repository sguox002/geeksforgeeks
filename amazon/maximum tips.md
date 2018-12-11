### Problem Summary
Given ntask, tips for person 1 A, tips for person 2 B, and person1 can at most take x orders, and person 2 can only take y orders.
return the max tips

### Idea
if x==0, then B takes all remaining orders
if y==0, then A takes all remaining orders
otherwise compare a[i]+subprob(A,B,x-1,y,start+1), B[i]+subprob(A,B,x,y-1,start+1)

### code
```cpp
int maxtips(vector<int>& A,vector<int>& B,int x,int y,int start)
{
    int n=A.size();
    if(start>=n) return 0;
    int ans=0;
    if(x<=0 && y) ans=B[start]+maxtips(A,B,x,y-1,start+1);
    else if(x && y<=0) ans=A[start]+maxtips(A,B,x-1,y,start+1);
    else ans=max(A[start]+maxtips(A,B,x-1,y,start+1),B[start]+maxtips(A,B,x,y-1,start+1));
    //cout<<start<<": "<<ans<<endl;
    return ans;
}
```

### comments
