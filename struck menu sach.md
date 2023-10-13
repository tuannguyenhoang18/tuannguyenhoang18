
#include <stdio.h>
#include <string.h>

struct Book {
    char title[50];
    char author[50];
    int quantity;
    char publishDate[20];
};

void addBook(struct Book books[], int *count) {
    printf("Enter book title: ");
    fflush(stdin);
    gets(books[*count].title);
    printf("Enter book author: ");
    fflush(stdin);
    gets(books[*count].author);
    printf("Enter quantity: ");
    scanf("%d", &books[*count].quantity);
    printf("Enter publish date (dd/mm/yyyy): ");
    fflush(stdin);
    gets(books[*count].publishDate);
    (*count)++;
}

void displayBooks(struct Book books[], int count) {
    printf("Books:\n");
    for (int i = 0; i < count; i++) {
        printf("Title: %s\n", books[i].title);
        printf("Author: %s\n", books[i].author);
        printf("Quantity: %d\n", books[i].quantity);
        printf("Publish Date: %s\n", books[i].publishDate);
        printf("--------------------\n");
    }
}

void editBook(struct Book books[], int count, char searchString[]) {
    for (int i = 0; i < count; i++) {
        if (strcmp(books[i].title, searchString) == 0 || strcmp(books[i].author, searchString) == 0) {
            printf("Enter new book title: ");
            fflush(stdin);
            gets(books[i].title);
            printf("Enter new book author: ");
            fflush(stdin);
            gets(books[i].author);
            printf("Enter new quantity: ");
            scanf("%d", &books[i].quantity);
            printf("Enter new publish date (dd/mm/yyyy): ");
            fflush(stdin);
            gets(books[i].publishDate);
            return;
        }
    }
    printf("Book not found!\n");
}

void searchByName(struct Book books[], int count, char searchString[]) {
    printf("Books found by Name:\n");
    int found = 0;
    for (int i = 0; i < count; i++) {
        if (strcmp(books[i].title, searchString) == 0) {
            printf("Title: %s\n", books[i].title);
            printf("Author: %s\n", books[i].author);
            printf("Quantity: %d\n", books[i].quantity);
            printf("Publish Date: %s\n", books[i].publishDate);
            printf("--------------------\n");
            found = 1;
        }
    }
    if (!found) {
        printf("No matching book found!\n");
    }
}

void searchByAuthor(struct Book books[], int count, char searchString[]) {
    printf("Books found by Author:\n");
    int found = 0;
    for (int i = 0; i < count; i++) {
        if (strcmp(books[i].author, searchString) == 0) {
            printf("Title: %s\n", books[i].title);
            printf("Author: %s\n", books[i].author);
            printf("Quantity: %d\n", books[i].quantity);
            printf("Publish Date: %s\n", books[i].publishDate);
            printf("--------------------\n");
            found = 1;
        }
    }
    if (!found) {
        printf("No matching book found!\n");
    }
}

void getTotalQuantity(struct Book books[], int count) {
    int total = 0;
    for (int i = 0; i < count; i++) {
        total += books[i].quantity;
    }
    printf("Total quantity of books: %d\n", total);
}

int main() {
    struct Book books[100];
    int count = 0;
    int choice;
    char searchString[100];

    do {
        printf("Menu:\n");
        printf("1. them sach\n");
        printf("2. xem danh sach\n");
        printf("3. chinh sua thong tin sach\n");
        printf("4. tim kiem theo ten va ten tac gia\n");
        printf("5. xem tong luong sach hien tai\n");

        printf("0. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                addBook(books, &count);
                break;
            case 2:
                displayBooks(books, count);
                break;
            case 3:
                printf("Enter book name or author to be edited: ");
                fflush(stdin);
                gets(searchString);
                editBook(books, count, searchString);
                break;
            case 4:
                printf("Enter book name to search: ");
                fflush(stdin);
                gets(searchString);
                searchByName(books, count, searchString);
                break;
            case 5:
                printf("Enter author name to search: ");
                fflush(stdin);
                gets(searchString);
                searchByAuthor(books, count, searchString);
                break;
      
            case 0:
                printf("Exiting the program...\n");
                break;
            default:
                printf("Invalid choice! Please enter a valid option.\n");
                break;
        }
        printf("\n");
    } while (choice != 0);

    return 0;
}

- 👋 Hi, I’m @tuannguyenhoang18
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
tuannguyenhoang18/tuannguyenhoang18 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
