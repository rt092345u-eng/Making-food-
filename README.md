<!DOCTYPE html>
<html>
<head>
    <title>Smart Cook AI</title>
    <style>
        body {
            font-family: Arial;
            background: linear-gradient(to right, #ff9966, #ff5e62);
            text-align: center;
            color: white;
        }
        input {
            padding: 12px;
            width: 300px;
            border-radius: 5px;
            border: none;
        }
        button {
            padding: 12px;
            background: black;
            color: white;
            border: none;
            cursor: pointer;
        }
        .card {
            background: white;
            color: black;
            margin: 20px auto;
            padding: 20px;
            width: 80%;
            border-radius: 15px;
        }
    </style>
</head>
<body>

<h1>🤖 Smart Cook AI</h1>
<p>Ingredients likho (comma se):</p>

<input type="text" id="ingredients" placeholder="aalu, tamatar">
<button onclick="findRecipes()">Find Recipes</button>

<div id="result"></div>

<script>

const recipes = [
    {
        name: "Aloo Tamatar Sabzi",
        items: ["aalu", "tamatar"],
        ingredients: ["Aalu", "Tamatar", "Masale"],
        steps: ["Aalu ubaalo", "Tamatar gravy banao", "Mix karo aur pakao"]
    },
    {
        name: "Aloo Fry",
        items: ["aalu"],
        ingredients: ["Aalu", "Oil", "Namak"],
        steps: ["Aalu kaato", "Oil me fry karo", "Serve karo"]
    },
    {
        name: "Paneer Masala",
        items: ["paneer", "tamatar"],
        ingredients: ["Paneer", "Tamatar", "Masale"],
        steps: ["Gravy banao", "Paneer daalo", "Cook karo"]
    }
];

function findRecipes() {
    let input = document.getElementById("ingredients").value.toLowerCase().split(",");
    let result = document.getElementById("result");
    result.innerHTML = "";

    let found = false;

    recipes.forEach(recipe => {
        let match = recipe.items.every(item => input.includes(item.trim()));

        if(match) {
            found = true;
            result.innerHTML += `
            <div class="card">
                <h2>${recipe.name}</h2>
                <h4>Ingredients:</h4>
                <ul>${recipe.ingredients.map(i => `<li>${i}</li>`).join("")}</ul>
                <h4>Steps:</h4>
                <ol>${recipe.steps.map(s => `<li>${s}</li>`).join("")}</ol>
            </div>
            `;
        }
    });

    if(!found) {
        result.innerHTML = "<h3>❌ Koi recipe nahi mili</h3>";
    }
}

</script>

</body>
</html> Making-food-
It is very helpfull and use full
