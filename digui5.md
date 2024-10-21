#include <iostream>
#include <iomanip>
using namespace std;
//已知n个整数 x_1,x_2,...,x_n，以及 1 个整数 k（k<n）。
//从 n 个整数中任选 k 个整数相加，可分别得到一系列的和。
//例如当 n=4，k=3，4 个整数分别为 3,7,12,19时，可得全部的组合与它们的和为：
// 3+7+12=22
// 3+7+19=29
// 7+12+19=38
// 3+12+19=34
//现在，要求你计算出和为素数共有多少种。
//例如上例，只有一种的和为素数：3+7+19=2。

const int N=21;
int n,k;
int q[N];
int arr[N];
int cnt=0;

bool isprime(int x){
    if(x<2) return false;
    for(int i=2;i<x/2;i++){
        if(x%i==0)
            return false;
    }
    return true;
}
void dfs(int x,int start){
    //if(x-1+n-start+1<k) return;
    if(x>k){//要求位置已满
    int sum=0;
        for(int i=1;i<=k;i++){
            sum+=arr[i];
        }
        if(isprime(sum)){
            cnt++;
        }
        return;
    }
    for(int i=start;i<=n;i++){
        if(x+n-start+1<k) return;
        arr[x]=q[i];
        dfs(x+1,i+1);//下一个位置上的数
        arr[x]=0;//回溯
    }
    return;
}
int main(){
    cin>>n>>k;
    for(int i=1;i<=n;i++){
        cin>>q[i];
    }
    dfs(1,1);
    cout<<cnt;
    return 0;
}
