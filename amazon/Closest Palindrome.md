### Problem Summary
Given a number N, find the closest palindrome number closest to N
see leetcode 564.Note it allows itself, which is not the same as leetcode

### idea
Let's build a list of candidate answers for which the final answer must be one of those candidates. Afterwards, choosing from these candidates is straightforward.

If the final answer has the same number of digits as the input string S, then the answer must be the middle digits + (-1, 0, or 1) flipped into a palindrome. For example, 23456 had middle part 234, and 233, 234, 235 flipped into a palindrome yields 23332, 23432, 23532. Given that we know the number of digits, the prefix 235 (for example) uniquely determines the corresponding palindrome 23532, so all palindromes with larger prefix like 23732 are strictly farther away from S than 23532 >= S.

If the final answer has a different number of digits, it must be of the form 999....999 or 1000...0001, as any palindrome smaller than 99....99 or bigger than 100....001 will be farther away from S.

### Implementation
```cpp
    long long closestPalindrome(long long num)
    {
        string n=to_string(num);
        int len=n.size();
        //long long num=stoll(n);
        vector<long long> vs;
        if(len>1)
        {
            string s(len-1,'9');

            long long c1=stoll(s)-num;
            long long c2=stoll(s)+2-num;
            if(c1) vs.push_back(c1);
            if(c2) vs.push_back(c2);
        }
        string s=n;//only need add 1 or keep the same or -1
        long long num1=stoll(n.substr(0,(len+1)/2));
        for(int i=-1;i<=1;i++)
        {
            long long num2=num1+i;
            n=s=to_string(num2);
            //reverse(n.begin(),n.end());//this will add an extra digit!!!wrong!
            //s+=n;
            for(int j=(len+1)/2;j<len;j++) s+=s[len-j-1];
            long long t=stoll(s)-num;
            vs.push_back(t);//allows itself
        }
        //sort(vs.begin(),vs.end());
        //absolute difference is smallest if tie choose smaller one
        int minabs=INT_MAX,ind=0;
        for(int i=0;i<vs.size();i++) if(abs(vs[i])<minabs) {minabs=abs(vs[i]);ind=i;}
        return num+vs[ind];
    }
```
