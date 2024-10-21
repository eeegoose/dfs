#1~n选任意个数，升序输出，有几种输出
  #include <iostream>
using namespace std;

const int N=20;

int n;
int st[20];//记录每个数的状态，0还没考虑，1选，2不选

void dfs(int x){
    if(x>n){
        for(int i=0;i<=n;i++){
            if(st[i]==1)
                cout<<i<<" ";
        }
        cout<<endl;
        return;
    }
    //选
    st[x]=1;
    dfs(x+1);
    st[x]=0;
    //不选
    st[x]=2;
    dfs(x+1);
    st[x]=0;
}
int main(){
    cin>>n;
    dfs(1);

    return 0;
}
