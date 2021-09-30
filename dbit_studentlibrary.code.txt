class Library:
    def __init__(self, listOfBooks):
        self.books = listOfBooks

    def displayAvailableBooks(self):
        print("Books present in this library are: ")
        for book in self.books:
            print("    	    * " + book)

    def borrowBook(self, bookname):
        if bookname in self.books:
            print(
                f"You have been issued {bookname} . Please keep it safe and return it within 30days")
            self.books.remove(bookname)
        else:
            print("Sorry , this book has already issued")
            return False

    def returnBook(self, bookName):
        self.books.append(bookName)
        print("THANKS for returning it")


class Student:
    def requestBook(self):
        self.book = input("enter the name of the book you need :  ")
        return self.book

    def returnBook(self):
        self.book = input("enter the name of the book you need to return: ")
        return self.book


if __name__ == "__main__":
    centralLibrary = Library(["Algoriyjs", "python", "UNIX"])
    student = Student()
    while(True):
        welcomeMsg = '''\n++++++////WELCOME TO DBIT STUDENTS LIBRARY\\\\\\\++++
        Please *choose* an option
        1. Listing all the books
        2. Request a book
        3. Return a book
        4. Exit the library'''
        print(welcomeMsg)
        a = int(input("Enter your choice:::: "))
        if a == 1:
            centralLibrary.displayAvailableBooks()
        elif a == 2:
            centralLibrary.borrowBook(student.requestBook())
        elif a == 3:
            centralLibrary.returnBook(student.returnBook())
        elif a == 4:
            print("THANKS FOR USING DBIT LIBRARY")
            exit()
        else:
            print("SORRY!!! INVALID CHOICE")
