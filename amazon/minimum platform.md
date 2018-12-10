### Problem Summary
Given a list of train arriving and departure time (in one day), return the min number of platform needed

### idea
No two trains can occupy the same platform at the same time. One idea is to connect the segments without overlap, which can use a single platform. But is this the global optimal?

### code
```
int minPlatforms(vector<vector<int>>& trains)
{
    sort(trains.begin(),trains.end());
    vector<vector<int>> vplatform; //platforms storing all trains
    vplatform.push_back(vector<int>(1,0)); //the first train
    for(int i=1;i<trains.size();i++)
    {
        //cout<<i<<":"<<trains[i][0]<<" "<<trains[i][1];
        int min_departure=INT_MAX;
        int min_ind=0;
        for(int j=0;j<vplatform.size();j++)
        {
            //connect the train to exisiting platform with smallest departure > our arriving
            int tdep=trains[vplatform[j].back()][1];
            //special case: arriving time=departure time, (not allowed), but it happens
            //in this case we cannot connect to the platform with same departure time
            //if(trains[i][0]==trains[i][1]) break;
            if(trains[i][0]>tdep && trains[i][1]>tdep) //the second condition to guarantee no same departure time on the platform
            {
                if(min_departure>tdep) {min_departure=tdep,min_ind=j;}
            }
        }
        if(min_departure==INT_MAX) {vplatform.push_back(vector<int>(1,i));/*cout<<"new plat"<<endl;*/}
        else {vplatform[min_ind].push_back(i);/*cout<<" "<<min_ind<<endl;*/}
    }
    return vplatform.size();
}
```
Another better approach:
sort the departure time and arriving time individually and then do a merge.
when arriving time[i]<=departure time[j], we need increase platform
otherwise we decrease the platform

```
int minPlatform1(vector<int>& arrival,vector<int>& departure)
{
    sort(arrival.begin(),arrival.end());
    sort(departure.begin(),departure.end());
    int ans=1,nplat=1;
    int i=1,j=0;//two pointers
    while(i<arrival.size() && j<departure.size())
    {
        if(arrival[i]>departure[j])
        {
            nplat--;j++;
        }
        else //<=
        {
            nplat++;i++;
            ans=max(nplat,ans);//cannot be less
        }
    }
    return ans;
}
```

The test case may have some problem. 
