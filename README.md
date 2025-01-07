# Methode 1 (Brute Fore Approach)

class Solution {
public:
    bool check(vector<int>& arr) {
      vector<int>A(arr.size(),0);
      A=arr;
      sort(A.begin(),A.end());
      vector<int>B(arr.size(),0);

      for(int r=0;r<=A.size();r++)
      {
        for(int i=0;i<A.size();i++)
        {
            B[(i+r)%A.size()]=A[i];
        }
        if(arr==B)
            return true;
      }
      return false;
    }
};

# Methode 2 (Optimal Approach)

class Solution {
public:
    bool check(vector<int>& arr) {
      int count=0,n=arr.size();
      for(int i=0;i<n;i++)
      {
        if(arr[i]>arr[(i+1)%n])
            count++;
      }
      if(count>1)
        return false;
    return true;
    }
};

# in this approach we initially take count =0 and compare if ith element is greater than i+1th element and for last element we checked if it is greater than the first element
# if array was sorted and rotated than this can happen atmost 1 time
