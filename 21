#include <iostream>
#include <vector>
#include <string>
#include <unordered_map>
#include <queue>
#include <algorithm>

using namespace std;

// Функция для нахождения k наиболее часто встречающихся строк
vector<string> topKFrequent(vector<string>& words, int k) {
    unordered_map<string, int> frequencyMap;

    // Подсчет частоты каждой строки
    for (const string& word : words) {
        frequencyMap[word]++;
    }

    // Используем приоритетную очередь для хранения строк с их частотой
    // Пара: (частота, слово)
    priority_queue<pair<int, string>> maxHeap;

    for (const auto& entry : frequencyMap) {
        maxHeap.push({entry.second, entry.first});
    }

    vector<string> result;

    // Извлекаем k наиболее частых слов
    for (int i = 0; i < k; i++) {
        if (!maxHeap.empty()) {
            result.push_back(maxHeap.top().second);
            maxHeap.pop();
        }
    }

    // Сортируем результат по лексикографическому порядку для слов с одинаковой частотой
    sort(result.begin(), result.end());

    return result;
}

int main() {
    vector<string> words = {"i", "love", "leetcode", "i", "love", "coding"};
    int k = 2;

    vector<string> topWords = topKFrequent(words, k);

    cout << "Top " << k << " frequent words: ";
    for (const string& word : topWords) {
        cout << word << " ";
    }
    cout << endl;

    return 0;
}
