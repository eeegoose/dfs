# dfs
#跳台阶问题:只能走一步或者两步，走n个台阶有多少种走法
#1---1
#2---2
#3---3
#4---5斐波那契数列
int f(int x)
{
    if (x == 1)
        return 1;
    else if (x == 2)
        return 2;
    else
        return f(x - 1) + f(x - 2);
}
int main()
{
    int res = f(39);
    cout << (res + 1) / 2;
    return 0;
}
