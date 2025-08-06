#include <iostream>
#include <string>
#include <filesystem> // C++17
#include <direct.h>   // For _mkdir, _chdir, _getcwd

using namespace std;
namespace fs = std::filesystem;

void displayCurrentDirectory() {
    char buffer[FILENAME_MAX];
    _getcwd(buffer, FILENAME_MAX);
    cout << "\nCurrent Directory: " << buffer << endl;
}

