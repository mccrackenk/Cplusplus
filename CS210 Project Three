/*Kaleb McCracken
CS 210
Professor Shakeel*/
#include <iostream>
#include <fstream>
#include <map>
#include <string>
using namespace std;

// Define the ItemTracker class
class ItemTracker {
private:
    map<string, int> itemsFrequency;
    const string dataFileName = "frequency.dat"; // Name of the data file

public:
    // Read data from the frequency.dat file
    void readDataFile() {
        ifstream dataFile(dataFileName);
        string itemName;
        int itemFrequency;

        while (dataFile >> itemName >> itemFrequency) {
            itemsFrequency[itemName] = itemFrequency;
        }

        dataFile.close();
    }

    // Save data to the frequency.dat file
    void saveDataFile() {
        ofstream dataFile(dataFileName);

        for (const auto& item : itemsFrequency) {
            dataFile << item.first << " " << item.second << endl;
        }

        dataFile.close();
    }

    // Add an item to the itemsFrequency map
    void addItem(string itemName) {
        itemsFrequency[itemName]++;
    }

    // Get the frequency of a specific item
    int getItemFrequency(string itemName) {
        return itemsFrequency[itemName];
    }

    // Print all items and their frequencies
    void printAllItemsFrequency() {
        for (const auto& item : itemsFrequency) {
            cout << item.first << " " << item.second << endl;
        }
    }

    // Print a histogram for items
    void printHistogram() {
        for (const auto& item : itemsFrequency) {
            cout << item.first << " ";
            for (int i = 0; i < item.second; i++) {
                cout << "*";
            }
            cout << endl;
        }
    }
};

int main() {
    ItemTracker tracker;
    tracker.readDataFile(); // Read existing data from the file

    int choice;
    string item;

    // Main menu loop
    do {
        cout << "Menu:\n"
            << "1. Add item\n"
            << "2. Print all items frequency\n"
            << "3. Print histogram\n"
            << "4. Exit\n"
            << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            cout << "Enter item name: ";
            cin >> item;
            tracker.addItem(item); // Add the entered item
            break;
        case 2:
            tracker.printAllItemsFrequency(); // Print all item frequencies
            break;
        case 3:
            tracker.printHistogram(); // Print histogram
            break;
        case 4:
            tracker.saveDataFile(); // Save data to the file
            cout << "Exiting program. Data saved." << endl;
            break;
        default:
            cout << "Invalid choice. Try again." << endl;
        }
    } while (choice != 4);

    return 0;
}
