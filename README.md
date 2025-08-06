#include <iostream>
#include <string>
#include <direct.h>   // For _mkdir, _chdir, _getcwd
#include <windows.h>  // For FindFirstFile, etc.

using namespace std;

void listFiles() {
    string pattern;
    cout << "\nEnter file pattern (e.g., *.*, *.txt): ";
    cin >> pattern;

    WIN32_FIND_DATA fileData;
    HANDLE hFind = FindFirstFile(pattern.c_str(), &fileData);

    if (hFind != INVALID_HANDLE_VALUE) {
        do {
            cout << fileData.cFileName << endl;
        } while (FindNextFile(hFind, &fileData));
        FindClose(hFind);
    } else {
        cout << "No files found.\n";
    }
}
