#include <iostream>
#include <stack>
#include <string>
using namespace std;

int main() {
    stack<string> undoStack;
    stack<string> redoStack;

    string currentText = "";
    int choice;

    while (true) {
        cout << "Current Text: " << currentText <<endl;
        cout << "1. Type Text"<<endl;
        cout << "3. Redo"<<endl;
        cout << "4. Exit"<<endl;
        cout << "2. Undo"<<endl;
        cout << "Enter choice: ";
        cin >> choice;
        cin.ignore(); 

        if (choice == 1) {
            undoStack.push(currentText);
            cout << "Enter new text: ";
            getline(cin, currentText);

            // Clear redo stack
            while (!redoStack.empty())
                redoStack.pop();
        }

        else if (choice == 2) {
            if (undoStack.empty()) {
                cout << "Nothing to undo.\n";
            } else {
                redoStack.push(currentText);
                currentText = undoStack.top();
                undoStack.pop();
            }
        }

        else if (choice == 3) {
            if (redoStack.empty()) {
                cout << "Nothing to redo.\n";
            } else {
                undoStack.push(currentText);
                currentText = redoStack.top();
                redoStack.pop();
            }
        }
        // loop breaks here
        else if (choice == 4) {
            break; 
        }

        else {
            cout << "Invalid choice.\n";
        }
    }

    return 0;
}
