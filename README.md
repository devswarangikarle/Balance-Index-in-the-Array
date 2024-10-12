# Balance-Index-in-the-Array

In a distant village, a young mathematician named Tara has been given a special challenge. She is handed an array A of size N, filled with mystical numbers. Her task is to find the smallest index i (where 1 ≤ i ≤ N) such that the sum of the first i elements is greater than or equal to the sum of the remaining elements of the array. Can you help Tara find this magical index where the balance shifts in her favor?


#include <iostream>
#include <vector>
#include <numeric>  
using namespace std;

void find_balance_index() {
    int N;
    cin >> N;  
    vector<int> A(N);
    
    for (int i = 0; i < N; ++i) {
        cin >> A[i];
    }

    long long total_sum = accumulate(A.begin(), A.end(), 0LL);
    long long prefix_sum = 0;

    for (int i = 0; i < N; ++i) {
        prefix_sum += A[i];  
        
        if (2 * prefix_sum >= total_sum) {
            cout << (i + 1) << endl; 
            return;
        }
    }
    
    cout << -1 << endl;
}

int main() {
    find_balance_index();  
    return 0;
}
