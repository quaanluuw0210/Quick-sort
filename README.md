# Quick-sort
Using quick sort and another sort type to solve problem
class Solution {
public:
void quick_sort(string &a,int l,int r)
{
    if(l>=r)
    {
        return;
    }
    char pivot=a[r];
    int i=l-1,j=l;
    while(j<=r)
    {
        if(a[j]<pivot)
        {
            i++;
            char temp=a[j];
            a[j]=a[i];
            a[i]=temp;
        }
        j++;
    }
    char temp=a[i+1];
    a[i+1]=a[r];
    a[r]=temp;
    quick_sort(a,l,i);
    quick_sort(a,i+2,r);
}

    bool isAnagram(string s, string t) {
        int cs=s.length();
        int ct=t.length();
        if(cs!=ct)
        {
            return false;
        }
        quick_sort(s,0,cs-1);
        quick_sort(t,0,ct-1);
        for(int i=0;i<cs;i++)
        {
            if(s[i]!=t[i])
            {
                return false;
            }
        }
        
        return true;
    }
};
