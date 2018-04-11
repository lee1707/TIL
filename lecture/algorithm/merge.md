# Today I learned
Merge Algorithm

# MergeSort(A[],n)
```
{
  if(n>1){
    Mid =ën/2û;
    B[0..Mid-1]=MergeSort(A[0..Mid-1], Mid);
    C[0..n-Mid-1] =MergeSort(A[Mid..n-1],n-Mid);
    A[0..n-1]=Merge(B[0..Mid-1], C[0..n-Mid-1],Mid,n-Mid);
  }
  return A;
}
```

# Merge() = Merge Function
```
Merge(B[],C[],n,m)
{
 i=j=k=0;
 while(i<n&&j<m){
  if(B[i]<=C[j])
    A[k++]=B[i++];
  else
    A[k++]=C[j++];
 }
 for(;i<n;i++)A[k++]=B[i];
 for(;j<m;j++)A[k++]=C[i];
 return A[0..n+m-1];
}
```

# Find Min Max
```
FindMinMax (A[],n,min,max)
{
  if(A[0]<A[1]){min=A[0];max=A[1];}
  else{min=A[1];max=A[0];}
  for(i=2;i<n;i+=2){
    if(A[i]<A[i+1]){small=A[i];large=A[i+1];}
    else{small=A[i+1];large=A[i];}
    if(small < min)min =small;
    if(large > max)max=large;
  }
}
```

# Find `N`st Min
```
int Selection(A[],n,i)
{
  Left=0;Right=n-1;
  p=Partition(A,n);
  if(i==p+1)returnA[p];
  else if(i<p+1)Selection(A[Left..p-1],(p-1)-Left+1,i);
    else Selection(A[p+1..Right-(p+1)-1,i-p-1);
}
```
Worst : O(n2), Avg : O(n)

