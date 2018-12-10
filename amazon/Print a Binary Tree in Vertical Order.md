### Problem Summary
Print tree in vertical order from left to right

### idea
left branch -1, right branch +1, 

### code
```cpp
void preorder(Node* root,map<int,vector<int>>& order,int off)
{
    if(!root) return;
    order[off].push_back(root->data);
    preorder(root->left,order,off-1);
    preorder(root->right,order,off+1);
}
void verticalOrder(Node *root)
{
    //Your code here
    map<int,vector<int>> order; //offset with the elements
    preorder(root,order,0);
    for(auto it=order.begin();it!=order.end();it++)
    {
        copy(it->second.begin(),it->second.end(),ostream_iterator<int>(cout," "));
        //cout<<endl;
    }
}
```
