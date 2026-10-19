# 🍿 Cinema Queue

Shared watch list for two. Search a title (TMDB), add it, drag to rank, mark what you're watching.
Your list is stored as `data.json` in a GitHub repo, so there's no database to set up.

## Setup

1. **Data repo** (private): on GitHub create a new **private** repo, e.g. `cinema-data`, and tick "Add a README" so it isn't empty. The app creates `data.json` itself.
2. **TMDB key**: free account at themoviedb.org → Settings → API → copy the *API Key* (v3).
3. **Config**: fill in [config.js](config.js) with `DATA_REPO` (`your-name/cinema-data`), the TMDB key and your two names.
4. **Run**: `python3 -m http.server 8000` in this folder, open http://localhost:8000
5. **Token** (once per person/device): GitHub → Settings → Developer settings → Fine-grained tokens → Generate.
   Repository access: *Only select repositories* → your data repo. Permissions → *Contents: Read and write*.
   Paste it into the app when asked. Both of you can use the same token or one each (the second needs to be a collaborator on the repo).

## Put it online
The site itself contains no list data, so it can be public: push this folder to a second (public) repo and enable GitHub Pages, or drag it onto Netlify Drop.

## Notes
- Changes show instantly and are saved to GitHub in the background. The other device picks them up within ~20 seconds.
- Every change is a commit, so you get history for free (and can undo in GitHub if needed).
- The TMDB key is visible in the page source; it's free and read-only, so that's fine here. Don't put the GitHub token in `config.js`.
