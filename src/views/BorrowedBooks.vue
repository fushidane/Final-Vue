<template>
  <div class="container">
    <h1>Borrowed Books</h1>
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Title</th>
          <th>Author</th>
          <th>Description</th>
          <th>Borrowed Date</th>
          <th>Return Date</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="borrowedBook in borrowedBooks" :key="borrowedBook.id">
          <td>{{ borrowedBook.id }}</td>
          <td>{{ getBookTitle(borrowedBook.book_id) }}</td>
          <td>{{ getBookAuthor(borrowedBook.book_id) }}</td>
          <td>{{ getBookDescription(borrowedBook.book_id) }}</td>
          <td>{{ borrowedBook.borrowed_date }}</td>
          <td>{{ borrowedBook.return_date }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
const books = [
      {
        "id": 1,
        "user_id": 1,
        "title": "The Great Gatsby",
        "author": "F. Scott Fitzgerald",
        "description": "A novel depicting the Roaring Twenties and the American Dream"
      },
      {
        "id": 2,
        "user_id": 2,
        "title": "To Kill a Mockingbird",
        "author": "Harper Lee",
        "description": "A story of racial injustice and the loss of innocence in the American South"
      },
      {
        "id": 3,
        "user_id": 3,
        "title": "1984",
        "author": "George Orwell",
        "description": "A dystopian novel depicting totalitarianism and government surveillance"
      },
      {
        "id": 4,
        "user_id": 4,
        "title": "Pride and Prejudice",
        "author": "Jane Austen",
        "description": "A classic novel exploring themes of love, reputation, and societal expectations"
      },
      {
        "id": 5,
        "user_id": 5,
        "title": "The Catcher in the Rye",
        "author": "J.D. Salinger",
        "description": "A novel reflecting teenage angst, alienation, and rebellion"
      },
      {
        "id": 6,
        "user_id": 6,
        "title": "The Lord of the Rings",
        "author": "J.R.R. Tolkien",
        "description": "An epic high-fantasy novel set in the fictional world of Middle-earth"
      },
      {
        "id": 7,
        "user_id": 7,
        "title": "The Alchemist",
        "author": "Paulo Coelho",
        "description": "A philosophical novel about a shepherd boy's journey to find treasure"
      },
      {
        "id": 8,
        "user_id": 8,
        "title": "One Hundred Years of Solitude",
        "author": "Gabriel Garcia Marquez",
        "description": "A magical realist novel portraying the Buendia family's generations in Macondo"
      },
      {
        "id": 9,
        "user_id": 9,
        "title": "Moby-Dick",
        "author": "Herman Melville",
        "description": "A tale of Captain Ahab's obsession with the white whale"
      },
      {
        "id": 10,
        "user_id": 10,
        "title": "Brave New World",
        "author": "Aldous Huxley",
        "description": "A dystopian novel exploring a future society's consequences of technological progress"
      },
      {
        "id": 11,
        "user_id": 11,
        "title": "The Picture of Dorian Gray",
        "author": "Oscar Wilde",
        "description": "A novel exploring the consequences of vanity and hedonism"
      },
      {
        "id": 12,
        "user_id": 12,
        "title": "Crime and Punishment",
        "author": "Fyodor Dostoevsky",
        "description": "A psychological novel focusing on the moral and mental struggles of Raskolnikov"
      },
      {
        "id": 13,
        "user_id": 13,
        "title": "Frankenstein",
        "author": "Mary Shelley",
        "description": "A gothic novel exploring the consequences of creating life"
      },
      {
        "id": 14,
        "user_id": 14,
        "title": "War and Peace",
        "author": "Leo Tolstoy",
        "description": "An epic novel depicting Russian society during the Napoleonic era"
      },
      {
        "id": 15,
        "user_id": 15,
        "title": "The Odyssey",
        "author": "Homer",
        "description": "An ancient Greek epic poem following Odysseus' journey back home"
      },
      {
        "id": 16,
        "user_id": 16,
        "title": "Les Misérables",
        "author": "Victor Hugo",
        "description": "A historical novel portraying the lives of several characters amidst social injustice"
      },
      {
        "id": 17,
        "user_id": 17,
        "title": "The Brothers Karamazov",
        "author": "Fyodor Dostoevsky",
        "description": "A philosophical novel examining faith, reason, and morality"
      },
      {
        "id": 18,
        "user_id": 18,
        "title": "The Count of Monte Cristo",
        "author": "Alexandre Dumas",
        "description": "An adventure novel following Edmond Dantès' quest for revenge"
      },
      {
        "id": 19,
        "user_id": 19,
        "title": "The Adventures of Sherlock Holmes",
        "author": "Arthur Conan Doyle",
        "description": "A collection of detective stories featuring Sherlock Holmes"
      },
      {
        "id": 20,
        "user_id": 20,
        "title": "The Hobbit",
        "author": "J.R.R. Tolkien",
        "description": "A fantasy novel about Bilbo Baggins' quest to reclaim the Lonely Mountain"
      },
      {
        "id": 21,
        "user_id": 1,
        "title": "The Grapes of Wrath",
        "author": "John Steinbeck",
        "description": "A novel focusing on the Joad family's experiences during the Great Depression"
      },
      {
        "id": 22,
        "user_id": 3,
        "title": "A Tale of Two Cities",
        "author": "Charles Dickens",
        "description": "A historical novel set in London and Paris before and during the French Revolution"
      },
      {
        "id": 49,
        "user_id": 7,
        "title": "The Handmaid's Tale",
        "author": "Margaret Atwood",
        "description": "A dystopian novel depicting a totalitarian society where women are oppressed"
      },
      {
        "id": 50,
        "user_id": 13,
        "title": "The Road",
        "author": "Cormac McCarthy",
        "description": "A post-apocalyptic novel following a father and son's journey in a barren world"
      }
];

const borrowedBooks = [
{
        "id": 1,
        "book_id": 7,
        "borrowed_date": "2023-01-01",
        "return_date": "2023-01-15"
      },
      {
        "id": 2,
        "book_id": 18,
        "borrowed_date": "2023-02-05",
        "return_date": "2023-02-20"
      },
      {
        "id": 3,
        "book_id": 5,
        "borrowed_date": "2023-03-10",
        "return_date": "2023-03-25"
      },
      {
        "id": 4,
        "book_id": 12,
        "borrowed_date": "2023-04-15",
        "return_date": "2023-04-30"
      },
      {
        "id": 5,
        "book_id": 8,
        "borrowed_date": "2023-05-20",
        "return_date": "2023-06-05"
      },
      {
        "id": 6,
        "book_id": 2,
        "borrowed_date": "2023-06-25",
        "return_date": "2023-07-10"
      },
      {
        "id": 7,
        "book_id": 16,
        "borrowed_date": "2023-07-30",
        "return_date": "2023-08-14"
      },
      {
        "id": 8,
        "book_id": 11,
        "borrowed_date": "2023-08-01",
        "return_date": "2023-08-15"
      },
      {
        "id": 9,
        "book_id": 14,
        "borrowed_date": "2023-09-05",
        "return_date": "2023-09-20"
      },
      {
        "id": 10,
        "book_id": 1,
        "borrowed_date": "2023-10-10",
        "return_date": "2023-10-25"
      },
      {
        "id": 11,
        "book_id": 19,
        "borrowed_date": "2023-11-15",
        "return_date": "2023-11-30"
      },
      {
        "id": 12,
        "book_id": 4,
        "borrowed_date": "2023-12-20",
        "return_date": "2024-01-05"
      },
      {
        "id": 13,
        "book_id": 9,
        "borrowed_date": "2024-02-01",
        "return_date": "2024-02-15"
      },
      {
        "id": 14,
        "book_id": 20,
        "borrowed_date": "2024-03-05",
        "return_date": "2024-03-20"
      },
      {
        "id": 15,
        "book_id": 13,
        "borrowed_date": "2024-04-10",
        "return_date": "2024-04-25"
      },
      {
        "id": 16,
        "book_id": 17,
        "borrowed_date": "2024-05-15",
        "return_date": "2024-05-30"
      },
      {
        "id": 17,
        "book_id": 3,
        "borrowed_date": "2024-06-20",
        "return_date": "2024-07-05"
      },
      {
        "id": 18,
        "book_id": 10,
        "borrowed_date": "2024-07-25",
        "return_date": "2024-08-09"
      },
      {
        "id": 19,
        "book_id": 6,
        "borrowed_date": "2024-08-30",
        "return_date": "2024-09-14"
      },
      {
        "id": 20,
        "book_id": 15,
        "borrowed_date": "2024-09-01",
        "return_date": "2024-09-15"
      },
      {
        "id": 21,
        "book_id": 1,
        "borrowed_date": "2024-10-05",
        "return_date": "2024-10-20"
      },
      {
        "id": 22,
        "book_id": 20,
        "borrowed_date": "2024-11-10",
        "return_date": "2024-11-25"
      },
      {
        "id": 23,
        "book_id": 4,
        "borrowed_date": "2024-12-15",
        "return_date": "2024-12-30"
      },
      {
        "id": 24,
        "book_id": 15,
        "borrowed_date": "2025-01-20",
        "return_date": "2025-02-04"
      },
      {
        "id": 25,
        "book_id": 3,
        "borrowed_date": "2025-02-25",
        "return_date": "2025-03-12"
      }
];

// Function to get book details by book ID
const getBookById = (id) => {
  return books.find(book => book.id === id);
};

// Functions to retrieve specific book details by book ID
const getBookTitle = (id) => getBookById(id)?.title || '';
const getBookAuthor = (id) => getBookById(id)?.author || '';
const getBookDescription = (id) => getBookById(id)?.description || '';
</script>

<style scoped>
.container {
  width: 1200px;
  margin: 0 auto;
  padding: 3%;
  text-align: center;
  background: linear-gradient(135deg, #235789, #8aaebd);
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h1 {
  color: #fff;
  font-size: x-large;
  font-weight: 800;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th, td {
  border: 1px solid #fff;
  padding: 8px;
  color: #fff;
}

th {
  background-color: #235789;
}

tbody tr:nth-child(even) {
  background-color: #8aaebd;
}

tbody tr:nth-child(odd) {
  background-color: #235789;
}
</style>
