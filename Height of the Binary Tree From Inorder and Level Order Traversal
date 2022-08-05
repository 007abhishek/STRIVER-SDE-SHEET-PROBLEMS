#include<bits/stdc++.h>
struct newtype{
 int left , right ;
 int height  ;
   newtype(int l , int r, int h){
       left = l;
       right = r;
       height = h;
   }
};

int heightOfTheTree(vector<int>& inorder, vector<int>& levelOrder, int N){
// Write your code here.
   queue<newtype>q;
   q.push({0,N-1,0});
   vector<int>pos(N+1,0);
   for(int i = 0 ; i<N ;i++){
       pos[inorder[i]] = i; // storing the position to get in order 1
   }
   int mxh = 0;
   for(int i = 0 ;i<N ;i++){
       int curr = levelOrder[i];
       int currPos = pos[curr] ; // ushe element ka kya position hai level order mein
       auto now = q.front();
       q.pop();
       int left = now.left;
       int right = now.right;
       int height = now.height;
       mxh = max(mxh,height);
       if(currPos>left){
//             means left child exist
           q.push({left,currPos-1 , height+1});
       }
       if(currPos<right){
//             means right child exits
           q.push({currPos+1,right,height+1});
       }
      
   }
   return mxh;
   
}
