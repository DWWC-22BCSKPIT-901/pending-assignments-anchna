#include <iostream>
#include <vector>
using namespace std;

int findCenter(vector<vector<int>>& edges) {
    if (edges[0][0] == edges[1][0] || edges[0][0] == edges[1][1]) {
        return edges[0][0];
    } else {
        return edges[0][1];
    }
}

int main() {
    vector<vector<int>> edges1 = {{1, 2}, {2, 3}, {4, 2}};
    cout << "Center of the graph: " << findCenter(edges1) << endl;

    vector<vector<int>> edges2 = {{1, 2}, {5, 1}, {1, 3}, {1, 4}};
    cout << "Center of the graph: " << findCenter(edges2) << endl;

    return 0;
}
