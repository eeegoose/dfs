//#排列与组合是常用的数学方法，其中组合就是从 n 个元素中抽出r 个元素（不分顺序且r≤n），我们可以简单地将 n个元素理解为自然数1,2,…,n，从中任取 r 个数。
#include <iostream>
#include <iomanip>
using namespace std;

const int N=21;

int n,r;
int arr[N];//存答案

void dfs(int x,int start){
    if(x>r){
        for(int i=1;i<=r;i++){
            cout<<setw(3)<<arr[i];
        }
        cout<<endl;
        return;
    }
    for(int i=start;i<=n;i++){
        arr[x]=i;
        dfs(x+1,i+1);
        arr[i]=0;
    }
}
int main(){
    cin>>n>>r;
    dfs(1,1);
    return 0;
}
