# 1064 Complete Binary Search Tree

1. 计算左子树，右子树的节点个数，找到中间的节点作为根节点。有点笨

   ```c++
   #include<iostream>
   #include<queue>
   #include<algorithm>
   #include<string.h>
   #include<math.h>
   using namespace std;
   int l[1005]={0};
   int r[1005]={0};
   int arr[1005]={0};
   int func(int left,int right){//cout<<left<<" "<<right<<endl;
       if(left>right)return -1;
       if(left==right)return left;
       int num=right-left;
       if(num==1){
           l[right]=left;
           return right;
       }
       int x=0,i;
       for(i=1;num>=pow(2,i);i++){
           num-=pow(2,i);
       }
       if(num>=pow(2,i-1)){
           x=pow(2,i)+left-1;
       }else
           x=pow(2,i-1)+num+left-1;
       l[x]=func(left,x-1);
       r[x]=func(x+1,right);
       return x;
   }
   int main(){
       int n;
       cin>>n;
       for(int i=0;i<n;i++){
           cin>>arr[i];
       }
       sort(arr,arr+n);
       memset(l,-1,sizeof(l));
       memset(r,-1,sizeof(r));
       queue<int> qe;
       qe.push(func(0,n-1));
       int flag=0;
       while(!qe.empty()){
           if(l[qe.front()]!=-1)qe.push(l[qe.front()]);
           if(r[qe.front()]!=-1)qe.push(r[qe.front()]);
           if(!flag)flag=1;
           else cout<<" ";
           cout<<arr[qe.front()];
           qe.pop();
       }
       return 0;
   }
   ```

2. `Inorder`+`Array`

   ```c++
   #include<iostream>
   #include<algorithm>
   #include<string.h>
   #include<math.h>
   using namespace std;
   int bst[1005]={0};
   int arr[1005]={0};
   int x=0,n;
   void inorder(int root){
       if(root>n)return;
       inorder(root*2);
       bst[root]=arr[x++];
       inorder(root*2+1);
   }
   int main(){
       cin>>n;
       for(int i=0;i<n;i++){
           cin>>arr[i];
       }
       sort(arr,arr+n);
       inorder(1);
       cout<<bst[1];
       for(int i=2;i<=n;i++){
           cout<<" "<<bst[i];
       }
       return 0;
   }
   ```

3. 1

