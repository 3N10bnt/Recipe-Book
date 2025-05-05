# Recipe-Book
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Recipe Book</title>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background-color: #f7f6f2;
      margin: 0;
      padding: 20px;
      color: #2d3436;
    }
    h1 {
      text-align: center;
      color: #6b8e23;
    }
    .recipes {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-top: 30px;
    }
    .card {
      background-color: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0px 3px 8px rgba(0, 0, 0, 0.1);
      transition: 0.3s;
    }
    .card:hover {
      transform: translateY(-5px);
      background-color: #f1f8e9;
    }
    .card h3 {
      color: #4e944f;
    }
    .search-bar {
      text-align: center;
      margin: 20px 0;
    }
    input[type="text"] {
      padding: 10px;
      width: 50%;
      border: 2px solid #6b8e23;
      border-radius: 8px;
    }
  </style>
</head>
<body>

<h1>My Recipe Book</h1>

<div class="search-bar">
  <input type="text" id="searchInput" placeholder="Search for a recipe...">
</div>

<div class="recipes" id="recipeList">
  <!-- Recipes will appear here -->
</div>

<script> 
    const recipes = [ 
    { title: "Avocado Toast", ingredients: "Avocado, Bread, Lemon" }, 
    { title: "Banana Smoothie", ingredients: "Banana, Milk, Honey" }, 
    { title: "Tomato Salad", ingredients: "Tomatoes, Basil, Olive Oil" }, 
    { title: "Veggie Stir Fry", ingredients: "Broccoli, Carrots, Soy Sauce" }, 
    { title: "Chicken Adobo", ingredients: "Chicken, Soy Sauce, Vinegar, Garlic" }, 
    { title: "Spaghetti Bolognese", ingredients: "Pasta, Ground Beef, Tomato Sauce" }, 
    { title: "Pancakes", ingredients: "Flour, Eggs, Milk, Sugar" }, 
    { title: "Garlic Butter Shrimp", ingredients: "Shrimp, Garlic, Butter, Parsley" }, 
    { title: "Tuna Sandwich", ingredients: "Tuna, Mayo, Bread, Lettuce" }, 
    { title: "Fried Rice", ingredients: "Rice, Egg, Mixed Vegetables, Soy Sauce" }, 
    { title: "Mango Float", ingredients: "Mango, Cream, Graham Crackers" }, 
    { title: "Grilled Cheese", ingredients: "Bread, Cheese, Butter" }, 
    { title: "Fruit Salad", ingredients: "Mixed Fruits, Cream, Condensed Milk" }, 
    { title: "Chicken Caesar Salad", ingredients: "Chicken, Romaine Lettuce, Caesar Dressing" } 
    ]; const recipeList = document.getElementById('recipeList'); const searchInput = document.getElementById('searchInput'); function displayRecipes(filter = "") { recipeList.innerHTML = ''; recipes.filter(recipe => recipe.title.toLowerCase().includes(filter.toLowerCase())) .forEach(recipe => { recipeList.innerHTML += ` <div class="card"> <h3>${recipe.title}</h3> <p><strong>Ingredients:</strong> ${recipe.ingredients}</p> </div> `; }); } searchInput.addEventListener('input', () => { displayRecipes(searchInput.value); }); displayRecipes(); </script> 


</body>
</html>
