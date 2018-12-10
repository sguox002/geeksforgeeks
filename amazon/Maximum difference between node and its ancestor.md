### Problem Summary
Given a binary tree, return the max difference between node and its child nodes

### Idea
The max difference is the node-min(subtree)

### Implementation
min(subtree) can be approached using recursion
```cpp

int minVal(Node* root, int& diff)
{
    if(!root) return INT_MAX;
    if(!root->left && !root->right) return root->data;
    int val=min(minVal(root->left,diff),minVal(root->right,diff));
    diff=max(diff,root->data-val);//this node max difference
    return min(val,root->data);
    
}
int maxDiff(Node* root)
{
    // Your code here 
    //note it asks for ancestor difference with all children, not immediate children
    int ans=INT_MIN;
    minVal(root,ans);//cout<<root->data<<": "<<ans<<endl;
    return ans;
}
```


