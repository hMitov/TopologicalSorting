#include <iostream>
#include <cstdio>
#include <vector>
#include <algorithm>

using namespace std;

#define MAX 100;

int n, v, used[MAX];
vector<int>a[MAX];
int G[MAX][2], ribs;
int topolArray[MAX];

int index = 0;

void spisuk_na_rebra() {
	cout << "Enter the number of ribs: ";
	cin >> ribs;

	for (int i = 0; i < ribs; i++) {
		for (int j = 0; j < 2; j++)
			cin >> G[i][j];
	}
}


void dfs(int k)
{
	for (int i = 0; i < a[k].size(); i++) {
		if (used[a[k][i]])
			continue;
		used[a[k][i]] = 1;
		dfs(a[k][i]);
	}
	topolArray[index++] = k;
}


int main() {
	spisuk_na_rebra();

	cout << "Enter the starting V: ";
	cin >> v;

	for (int i = 0; i < ribs; i++) {
		a[G[i][0]].push_back(G[i][1]);
	}

	for (int i = 0; i < ribs; i++)
		sort(a[i].begin(), a[i].end());

	used[v] = 1;
	dfs(v);

	for (int i = 0; i < index; i++) {
		cout << topolArray[i] << " ";
	}
	cout << endl;

	return 0;
}
