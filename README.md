#include <iostream>
#include <string>
#include <filesystem> 
#include <direct.h>   

using namespace std;
namespace fs = std::filesystem;

void displayCurrentDirectory() {
    char buffer[FILENAME_MAX];
    _getcwd(buffer, FILENAME_MAX);
    cout << "\nCurrent Directory: " << buffer << endl;
}

