#include <iostream>
#include <vector>
#include <queue>
using namespace std;

vector<vector<int>> updateMatrix(vector<vector<int>>& mat) {
    int m = mat.size();
    int n = mat[0].size();
    vector<vector<int>> distances(m, vector<int>(n, INT_MAX));
    queue<pair<int, int>> q;
    for (int i = 0; i < m; ++i) {
        for (int j = 0; j < n; ++j) {
            if (mat[i][j] == 0) {
                distances[i][j] = 0;
                q.push({i, j});
            }
        }
    }

    vector<pair<int, int>> directions = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};

    while (!q.empty()) {
        auto [x, y] = q.front();
        q.pop();

        for (auto [dx, dy] : directions) {
            int nx = x + dx;
            int ny = y + dy;

            if (nx >= 0 && nx < m && ny >= 0 && ny < n) {
                if (distances[nx][ny] > distances[x][y] + 1) {
                    distances[nx][ny] = distances[x][y] + 1;
                    q.push({nx, ny});
                }
            }
        }
    }

    return distances;
}

int main() {
    vector<vector<int>> mat1 = {{0, 0, 0}, {0, 1, 0}, {0, 0, 0}};
    vector<vector<int>> result1 = updateMatrix(mat1);
    cout << "Output for Example 1:" << endl;
    for (const auto& row : result1) {
        for (int cell : row) {
            cout << cell << " ";
        }
        cout << endl;
    }

    vector<vector<int>> mat2 = {{0, 0, 0}, {0, 1, 0}, {1, 1, 1}};
    vector<vector<int>> result2 = updateMatrix(mat2);
    cout << "Output for Example 2:" << endl;
    for (const auto& row : result2) {
        for (int cell : row) {
            cout << cell << " ";
        }
        cout << endl;
    }

    return 0;
}
