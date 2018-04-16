# Today I learned
**Algorithm2**
1. Edit Distance
2. Shortest Path
3. Scale

# Edit  Distance
- input: String array X[1..n], Y[1..m]<br>
  insert ins, delete del, change chg<br>
- output: E[n][m] : Edit Distance
```
ED(n,X[],m,Y[],ins,del,chg)
{
  int E[n+1][m+1],i,j;
  E[0][0]=0;
  for(i=1;i<n+1;i++) //첫 열의 초기화
    E[i][0]=E[i-1][0]+del;
  for(j=1;j<m+1;j++) //첫 행의 초기화
    E[0][j]=E[0][j-1]+ins;
  for(i=1;i<n+1;i++)
    for(j=1;j<m+1;j++){
      c=(X[i]==Y[j])?0:chg;
      E[i][j]=min(E[i-1][j]+del, E[i][j-1]+ins, E[i-1][j-1]+c);
    }
  return E[n][m];
}
```

# Shortest Path
- input: G=(V,E)
- output: D[][]: Shortest Path
```
Floyd(G)
{
  D[][]←입력 간선의 인접 행렬로 초기화
  for(k=1부터|V|까지)
    for(i=1부터|V|까지)//시작 정점
      for(j=1부터|V|까지)//끝 정점
        if(D[i][j]>D[i][k]+D[k][j])
          D[i][j]=D[i][k]+D[k}[j];
 return D[][];
}
```

# Scale
- input: Scale number<br>
  w[1..n]: Scale weight<br>
  M: Object weight
- output: S[n][M]: can scale hold weight M?
```
Scale(n,w[],M)
{
  int i,k,S[0..n][0..M];
  for(i=0;i<=n;i++)S[i][0]=1;
  for(k=1;k<=M;k++)S[0][k]=0;
  for(i=1;i<=n;i++)
    for(k=1;k<=M;k++)
      if(k-w[i]<0)
        S[i][k]=S[i-1][k];
      else
        S[i][k]=max(S[i-1][k],S[i-1][k-w[i]]);
  return S[n][M];
}
```


