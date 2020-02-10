next_permutation을 이용해 조합(Combinataion) 구하기
=================================================

원리
---

> 전체 n개의 원소들 중에서 k개를 뽑는 조합(=nCk)을 구한다면 n개의 벡터 원소에 1을 k개 0을 나머지인 n-k개 집어넣어서 순열을 돌리고 
> 1에 해당하는 인덱스만 가져오면 된다.

* * *

'''
#include <stdio.h>
#include <vector>
#include <algorithm>

using namespace std;

int main (){
   // 1부터 6까지 담을 벡터
	vector<int> n;
	// 1부터 6까지 생성
	for(int i=0; i<6; i++){
		n.push_back(i+1);
	}
	// 0과1을 저장 할 벡터 생성
	vector<int> ind;
	// k=4, 4개를 뽑으니까
	int k = 4;
	// k개의 1 추가
	for(int i=0; i<k; i++){
		ind.push_back(1);
	}
	// 2개(6개-2개)의 0 추가
	for(int i=0; i<n.size()-k; i++){
	   ind.push_back(0);
	}
	// 정렬
	sort(ind.begin(), ind.end());
	//순열
	do{
	// 출력
	for(int i=0; i<ind.size(); i++){
	if(ind[i] == 1){
		printf("%d ", n[i]);
		}
	}
	printf("\n");
	} while(next_permutation(ind.begin(), ind.end()));
	return 0;
	
	
}
'''
