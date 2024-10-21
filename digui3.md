#全排列
const int N=20;

int n;
bool st[N];//记录每个数的状态,true选过，false没选过
int arr[N];//存答案

void dfs(int x){
    if(x>n){
        for(int i=1;i<=n;i++){
            cout<<setw(5)<<arr[i];
        }
        cout<<endl;
        return;
    }
    for(int i=1;i<=n;i++){
        if(!st[i]){
            st[i]=true;
            arr[x]=i;
            dfs(x+1);
            st[i]=false;
            arr[x]=0;
        }
    }
}
int main(){
    cin>>n;
    dfs(1);
    return 0;
}
