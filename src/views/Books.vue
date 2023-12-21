<template>
    <div class="container">
      <h1>Books List</h1>
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>User ID</th>
            <th>Title</th>
            <th>Author</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="book in books" :key="book.id">
            <td>{{ book.id }}</td>
            <td>{{ book.user_id }}</td>
            <td>{{ book.title }}</td>
            <td>{{ book.author }}</td>
            <td>{{ book.description }}</td>
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
