Documentation Structure For Movie App...

1; Sign Up Page

Collect: Name, Email, Password, Role (default = user).

Store in your backend (or local storage for demo).


2; Login Page

User enters email + password.

If role = user → redirect to User Dashboard.

If role = admin → redirect to Admin Dashboard.


3; User Dashboard

Favorites list.

Recently searched movies.

Option to add/remove favorites (CRUD).


4; Admin Dashboard

List of all users.

View user activity (last login, last movie searched, etc.).

Option to delete a user (CRUD: Delete).

(Optional) Promote/demote users.

  // Render movies neatly in rows
    // function renderMovies(movies) {
    //   moviesContainer.innerHTML = "";
    //   movies.forEach(movie => {
    //     const col = document.createElement("div");
    //     col.className = "col-md-4 col-lg-3";

    //     col.innerHTML = `
    //       <div class="card shadow-sm movie-card">
    //         <img src="${movie.Poster !== "N/A" ? movie.Poster : 'https://via.placeholder.com/300x450?text=No+Image'}" class="card-img-top movie-poster" alt="${movie.Title}">
    //         <div class="card-body text-center">
    //           <h6 class="card-title">${movie.Title}</h6>
    //           <p class="text-muted">${movie.Year}</p>
    //           <button class="btn btn-sm btn-outline-danger favorite-btn" data-movie='${JSON.stringify(movie)}'>❤️ Favorite</button>
    //           <button class="btn btn-sm btn-outline-light details-btn" data-id="${movie.imdbID}">ℹ️ Details</button>
    //         </div>
    //       </div>
    //     `;

    //     moviesContainer.appendChild(col);
    //   });

    //   // Handle favorite button clicks
    //   document.querySelectorAll(".favorite-btn").forEach(btn => {
    //     btn.addEventListener("click", () => {
    //       const movie = JSON.parse(btn.getAttribute("data-movie"));
    //       saveFavorite(movie);
    //     });
    //   });

    //   // Handle details button clicks
    //   document.querySelectorAll(".details-btn").forEach(btn => {
    //     btn.addEventListener("click", async () => {
    //       const imdbID = btn.getAttribute("data-id");
    //       await showMovieDetails(imdbID);
    //     });
    //   });
    // }

    // // Save favorites to localStorage
    // function saveFavorite(movie) {
    //   let favorites = JSON.parse(localStorage.getItem("favorites")) || [];
    //   if (!favorites.some(fav => fav.imdbID === movie.imdbID)) {
    //     favorites.push(movie);
    //     localStorage.setItem("favorites", JSON.stringify(favorites));
    //     alert(`${movie.Title} added to Favorites!`);
    //   } else {
    //     alert(`${movie.Title} is already in Favorites!`);
    //   }
    // }

    // // Show movie details in modal
    // async function showMovieDetails(imdbID) {
    //   const url = `https://www.omdbapi.com/?apikey=${apiKey}&i=${imdbID}&plot=full`;
    //   const response = await fetch(url);
    //   const data = await response.json();

    //   // Populate modal
    //   document.getElementById("movieTitleModal").textContent = data.Title;
    //   document.getElementById("moviePosterModal").src = data.Poster !== "N/A" ? data.Poster : 'https://via.placeholder.com/300x450?text=No+Image';
    //   document.getElementById("movieYear").textContent = data.Year;
    //   document.getElementById("movieGenre").textContent = data.Genre;
    //   document.getElementById("movieDirector").textContent = data.Director;
    //   document.getElementById("movieActors").textContent = data.Actors;
    //   document.getElementById("moviePlot").textContent = data.Plot;
    //   document.getElementById("movieRating").textContent = data.imdbRating;

    //   // Show modal
    //   const modal = new bootstrap.Modal(document.getElementById("movieDetailsModal"));
    //   modal.show();
    // }

    // // Search button click event
    // searchBtn.addEventListener("click", async () => {
    //   const query = searchInput.value.trim();
    //   if (query) {
    //     const movies = await fetchMovies(query);
    //     renderMovies(movies);
    //   }
    // });

    // // Search on Enter key press
    // searchInput.addEventListener("keypress", async (e) => {
    //   if (e.key === "Enter") {
    //     searchBtn.click();
    //   }
    // });