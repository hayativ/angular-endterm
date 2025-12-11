# Angular End Term Project Requirements

Total: 10 points

4 points for project defense

6 points for project code

Bonuses: each +0.5 points, maximum +3 extra points

## Defense (4 points):
1. Explain project structure: modules, components, routing.
2. Explain authentication: signup, login, logout, guards.
3. Explain Observables and RxJS usage, including how the search and the favorites feature works.
4. Answer one technical question (Data Binding, RxJS, Routing, PWA, Service Workers).

## Code Requirements:

1. Authentication:
    * Use Firebase Authentication. Custom JWT is allowed only if fully implemented and deployed online.
    * Signup must include email with email syntax validation, password, repeat password, and password complexity validation (8 + chars, one special, one number).
    * Repeat password must match.
    * Login and logout must work.
    * Auth guard must protect at least one route (/profile, /dashboard, etc.) and redirect to /login if unauthenticated.
    * Auth state must be observable.

2. Required Pages. At least seven pages:
    * Home/About Us
    * Login
    * Signup
    * Items List
    * Item Details
    * Favorites / Bookmarks / Cart
    * Protected page for logged-in users only (Profile or Dashboard)

3. External API and Search System:
    * You must use a real external API or a deployed backend. Localhost APIs are not allowed.
    * API must have a list endpoint and a details endpoint.
    * List must include at least 20 items.
    * List view must show at least 5 items.
    * Details view must show at least 7 fields.

4. Search and filtering rules:
    * If the API supports search parameters, you must use them with query parameters in the URL and call the API with RxJS debounceTime, distinctUntilChanged, and switchMap. Local-only search is not allowed in this case.
    * If the API does not support search, then you must have and use at least three filter categories with query parameters. Local search is allowed only in this case and must use RxJS with debounceTime.
    * Pagination with query parameters (list of how many items on a page, (for example 5, 10, so on)) and navigate between pages.

5. Data Interfaces:
    * Create TypeScript interfaces describing the data you receive from the API.
    * Interfaces must include all fields you display in your templates.
    * Item Details must show at least seven fields.

6. Routing Requirements:
    * You must implement all required routes.
    * You must have at least one protected route with a guard.

7. RxJS Requirements:
    * You must use RxJS for real logic, not just HttpClient.
    * You must use debounceTime, distinctUntilChanged, and switchMap in your search.
    * Use Observables from ActivatedRoute for route params or query params.
    * Use catchError for handling API errors.
    * Use at least three meaningful RxJS operators in total.

8. PWA and Service Worker:
    * Your app must be a PWA.
    * You must include a manifest with icons.
    * Service worker must be active.
    * App shell must be cached.
    * You must implement at least one data caching strategy.
    * Your app must display an offline message when offline.

9. Personalized Feature: (Favorites or Bookmarks or Cart):
    * For not logged-in users:
        * Favorites must be saved in localStorage.
        * Favorites must stay after page reload.
        * Store a list of item IDs or URLs.
    * For logged-in users:
        * Favorites must be stored in Firestore under the user’s UID.
        * Favorites must load automatically after login.
        * Adding or removing favorites must update Firestore.
        * Local favorites may be merged with server favorites on first login.
        * (include UI message)

10. Profile Picture Upload. Each authenticated user must have a profile page where they
can:
    * Upload a profile picture (.jpg / .png)
    * Compress it in a Web Worker (basic compression OK)
    * Save image to Firebase Storage
    * Save image URL to Firestore under user’s profile
    * Render the uploaded picture in the header or sidebar

Grading Criteria for Code (6 points):
* 1 point — authentication: Firebase setup, signup, login, logout, password rules, repeat password, guard works.
* 1 point — API and data models: Real API, list and details endpoints, seven fields shown, interfaces created. CSS, templates and ts are fully separated.
* 1 point — search, filters, and pagination: Correct search system depending on API capabilities based on query params — search or filters, RxJS debounce, pagination.
* 0.5 point — routing: seven required pages, protected route.
* 0.5 point — PWA: Manifest, service worker, caching, offline behavior.
* 1 point — favorites feature: Works in localStorage for guests, works in Firestore for logged-in users, loads correctly after login, full UI implemented.
* 1 point — Profile page for logged-in users with profile picture upload. Image is compressed or processed (optionally via Web Worker), uploaded to Firebase Storage, and the photo URL is saved in Firestore. UI updates and displays the stored profile picture.

Bonus points (0.5 point each, max +3 points)
* NgRx Store (state, actions, reducer, selectors)
* Custom offline page and improved offline UX
* Push notifications
* High-quality CSS & responsive UI
* Full tests coverage
* Multi-language support (i18n) (at least 2 of languages: KZ, EN, RU)