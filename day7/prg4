#include <iostream>
#include <vector>
#include <unordered_map>
#include <unordered_set>
#include <algorithm>
using namespace std;

class UnionFind {
public:
    vector<int> parent;

    UnionFind(int size) {
        parent.resize(size);
        for (int i = 0; i < size; ++i) {
            parent[i] = i;
        }
    }

    int find(int x) {
        if (parent[x] != x) {
            parent[x] = find(parent[x]); 
        }
        return parent[x];
    }

    void unite(int x, int y) {
        int rootX = find(x);
        int rootY = find(y);
        if (rootX != rootY) {
            parent[rootX] = rootY;
        }
    }
};

vector<vector<string>> accountsMerge(vector<vector<string>>& accounts) {
    unordered_map<string, int> emailToIndex; 
    unordered_map<string, string> emailToName; 
    int n = accounts.size();

    UnionFind uf(n);

    for (int i = 0; i < n; ++i) {
        string name = accounts[i][0];
        for (int j = 1; j < accounts[i].size(); ++j) {
            string email = accounts[i][j];
            emailToName[email] = name;
            if (emailToIndex.find(email) != emailToIndex.end()) {
                uf.unite(i, emailToIndex[email]);
            } else {
                emailToIndex[email] = i;
            }
        }
    }

    unordered_map<int, vector<string>> indexToEmails;
    for (const auto& [email, index] : emailToIndex) {
        int rootIndex = uf.find(index);
        indexToEmails[rootIndex].push_back(email);
    }

    vector<vector<string>> result;
    for (const auto& [index, emails] : indexToEmails) {
        vector<string> mergedAccount;
        mergedAccount.push_back(emailToName[emails[0]]); 
        vector<string> sortedEmails = emails;
        sort(sortedEmails.begin(), sortedEmails.end());
        mergedAccount.insert(mergedAccount.end(), sortedEmails.begin(), sortedEmails.end());
        result.push_back(mergedAccount);
    }

    return result;
}

int main() {
    vector<vector<string>> accounts1 = {
        {"John", "johnsmith@mail.com", "john_newyork@mail.com"},
        {"John", "johnsmith@mail.com", "john00@mail.com"},
        {"Mary", "mary@mail.com"},
        {"John", "johnnybravo@mail.com"}
    };

    vector<vector<string>> result1 = accountsMerge(accounts1);
    cout << "Merged Accounts (Example 1):" << endl;
    for (const auto& account : result1) {
        for (const auto& field : account) {
            cout << field << " ";
        }
        cout << endl;
    }
    vector<vector<string>> accounts2 = {
        {"Gabe", "Gabe0@m.co", "Gabe3@m.co", "Gabe1@m.co"},
        {"Kevin", "Kevin3@m.co", "Kevin5@m.co", "Kevin0@m.co"},
        {"Ethan", "Ethan5@m.co", "Ethan4@m.co", "Ethan0@m.co"},
        {"Hanzo", "Hanzo3@m.co", "Hanzo1@m.co", "Hanzo0@m.co"},
        {"Fern", "Fern5@m.co", "Fern1@m.co", "Fern0@m.co"}
    };

    vector<vector<string>> result2 = accountsMerge(accounts2);
    cout << "\nMerged Accounts (Example 2):" << endl;
    for (const auto& account : result2) {
        for (const auto& field : account) {
            cout << field << " ";
        }
        cout << endl;
    }

    return 0;
}
