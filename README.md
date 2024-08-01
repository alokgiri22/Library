// # Library
//💡 Key Features: 🔹Add Books 🔹Show Available Books 🔹Issue Books 🔹Return Books
<br>

import java.util.Arrays;

class Library{
    String [] books;
    int numberOfBooks;
    Library(){
        this.books = new String [100];
        this.numberOfBooks = 0;
    }
    void addBooks(String books){
        this.books[numberOfBooks] = books;
        numberOfBooks++;
        System.out.println("* "+ books + " has been added.");
    }

    void showAvailableBooks(){
        System.out.println("\nAvailable books list ; " );
        for(String books : this.books){
            if (books == null){
                continue;
            }
            System.out.println("* " + books);
        }
    }

    void issueBooks(String books){
        for (int i=0; i<this.books.length; i++){
            if (this.books[i].equals(books)){
                System.out.println("\n** " + books + " has been issued. **");
                this.books[i] = null;
                return;
            }
        }
        System.out.println("Book is not available!!");
    }

    void returnBooks(String books){
        System.out.println();
        addBooks(books);
        System.out.print("  (returned)");
        System.out.println();
    }
}
public class OnlineLibrary_61 {
    public static void main(String[] args) {
        System.out.println("Books Added!!");
        Library library = new Library();
        library.addBooks("Gulliver's Travels");
        library.addBooks("Diary of a Young Girl");
        library.addBooks("Rich Dad Poor Dad");
        library.addBooks("Sapiens by Yuval Noah Harari");

        library.showAvailableBooks();

        library.issueBooks("Diary of a Young Girl");
        library.showAvailableBooks();

        library.returnBooks("Diary of a Young Girl");
        library.showAvailableBooks();


    }
}
