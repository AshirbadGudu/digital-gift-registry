# Digital Gift Registry

## Overview

Digital Gift Registry is a web application built with React and Firebase that allows users to create and share gift ideas. Users can log in securely with Google authentication, create gift suggestions with rich text descriptions, and share them publicly. Other users can discover gift ideas, like them, and view user profiles to see gift ideas from specific creators.

## Features

*   **Secure Authentication:**
    *   Google Authentication via Firebase.
*   **Gift Idea Creation:**
    *   Users can create gift ideas with a title and detailed description.
    *   Rich text editor for formatting descriptions (e.g., using Quill, Draft.js, or TinyMCE).
*   **Public Sharing:**
    *   Users can make their gift ideas public for others to discover.
*   **Discovery and Liking:**
    *   Browse and discover gift ideas from other users.
    *   Like gift ideas to save them to a personal "Liked Gifts" page.
*   **Search and Filtering:**
    *   Search for gift ideas based on keywords.
    *   Sort gift ideas by popularity (likes), date created, or relevance.
    *   Filter gift ideas by category (if you implement categories).
*   **User Profiles:**
    *   View user profiles to see all gift ideas created by a specific user.
*   **Realtime Database:**
    *   Gift ideas are stored in Firebase Realtime Database for real-time updates.
*   **Responsive Design:**
    *   The application is designed to be responsive and work on various devices (desktops, tablets, and mobile phones).

## Additional Ideas (Creative Inputs)

*   **Gift Categories:** Allow users to categorize their gift ideas (e.g., "Tech," "Books," "Experiences," "Home Goods"). This will improve filtering and discovery.
*   **Image Uploads:** Enable users to upload images to accompany their gift ideas.  This makes the gift ideas more visually appealing.
*   **Collaborative Gift Ideas:** Allow multiple users to contribute to a single gift idea.  This is great for group gifts.
*   **Privacy Settings:**  In addition to "Public," add options like "Friends Only" or "Private" for gift ideas.
*   **Wishlist Integration:**  Allow users to link gift ideas to products on external e-commerce sites (e.g., Amazon, Etsy).  This makes it easier for others to purchase the gift.
*   **Commenting System:**  Enable users to comment on gift ideas to ask questions or provide suggestions.
*   **Social Sharing:**  Allow users to easily share gift ideas on social media platforms.
*   **Theming:** Implement light and dark themes.
*   **"Gifted" Status:** Allow the original poster to mark a gift idea as "Gifted" once they've received it.
*   **Email Notifications:** Notify users when someone likes their gift idea or comments on it.

## Technology Stack

*   **Frontend:** React
*   **Backend:** Firebase (Authentication, Realtime Database)
*   **Rich Text Editor:** (e.g., Quill, Draft.js, TinyMCE)
*   **Styling:** CSS Modules, Styled Components, or Material-UI (choose one)

## Folder Structure

```
digital-gift-registry/
├── src/
│   ├── components/          # Reusable React components
│   │   ├── Auth/             # Authentication components
│   │   │   ├── Login.jsx
│   │   │   └── Logout.jsx
│   │   ├── GiftIdea/         # Components related to gift ideas
│   │   │   ├── GiftIdeaCard.jsx   # Display a single gift idea
│   │   │   ├── GiftIdeaForm.jsx   # Form for creating/editing gift ideas
│   │   │   ├── GiftIdeaList.jsx   # Display a list of gift ideas
│   │   │   └── GiftIdeaDetails.jsx # Display full details of a gift idea
│   │   ├── User/             # Components related to user profiles
│   │   │   ├── UserProfile.jsx
│   │   │   └── UserGiftIdeas.jsx
│   │   ├── UI/               # Generic UI components (buttons, inputs, etc.)
│   │   │   ├── Button.jsx
│   │   │   ├── Input.jsx
│   │   │   └── LoadingSpinner.jsx
│   │   ├── Search/           # Search bar component
│   │   │   └── SearchBar.jsx
│   │   └── Common/           # Components used across the application
│   │       └── RichTextEditor.jsx
│   ├── pages/               # React components for different routes/pages
│   │   ├── Home.jsx           # Home page (list of gift ideas)
│   │   ├── LikedGifts.jsx     # Page displaying liked gift ideas
│   │   ├── Profile.jsx        # User profile page
│   │   ├── CreateGift.jsx     # Page for creating a new gift idea
│   │   └── GiftDetails.jsx    # Page for viewing a single gift idea
│   ├── context/             # React Context for state management (optional)
│   │   └── AuthContext.jsx
│   ├── services/            # Firebase data fetching and utility functions
│   │   └── firebase.js      # Firebase configuration and initialization
│   │   └── giftIdeaService.js # Functions for interacting with gift ideas in Firebase
│   │   └── userService.js   # Functions for interacting with user data in Firebase
│   ├── App.jsx              # Main application component
│   ├── index.jsx            # Entry point for React
│   ├── index.css            # Global styles
│   └── firebase-config.js   # Firebase configuration
├── public/
│   ├── index.html         # HTML entry point
│   └── ...
├── .gitignore
├── package.json
├── README.md
└── webpack.config.js      # (If using Webpack)
```

## Component Breakdown

Here's a more detailed look at some of the key components:

*   **`Auth/`**
    *   `Login.jsx`: Handles Google authentication using Firebase.
    *   `Logout.jsx`: Handles user logout.
*   **`GiftIdea/`**
    *   `GiftIdeaCard.jsx`: Displays a brief summary of a gift idea (title, short description, likes, creator).  Used in lists.
    *   `GiftIdeaForm.jsx`:  A form for creating and editing gift ideas.  Includes the rich text editor.
    *   `GiftIdeaList.jsx`: Displays a list of `GiftIdeaCard` components. Handles sorting and filtering.
    *   `GiftIdeaDetails.jsx`: Displays the full details of a gift idea, including the rich text description, likes, creator information, and comments (if implemented).
*   **`User/`**
    *   `UserProfile.jsx`: Displays user information (e.g., profile picture, username) and a link to their gift ideas.
    *   `UserGiftIdeas.jsx`: Displays a list of gift ideas created by a specific user.
*   **`UI/`**
    *   `Button.jsx`: A reusable button component.
    *   `Input.jsx`: A reusable input component.
    *   `LoadingSpinner.jsx`: A component to display a loading spinner while data is being fetched.
*   **`Search/`**
    *   `SearchBar.jsx`: A search bar component that allows users to search for gift ideas.
*   **`Common/`**
    *   `RichTextEditor.jsx`: A wrapper component for the chosen rich text editor (Quill, Draft.js, or TinyMCE).  Handles the editor's configuration and integration with the form.
*   **`pages/`**
    *   `Home.jsx`: The main page, displaying a list of gift ideas.
    *   `LikedGifts.jsx`: Displays a list of gift ideas that the user has liked.
    *   `Profile.jsx`: Displays the user's profile and their gift ideas.
    *   `CreateGift.jsx`: A page containing the `GiftIdeaForm` for creating new gift ideas.
    *   `GiftDetails.jsx`: A page displaying the `GiftIdeaDetails` component for a specific gift idea.
*   **`context/`**
    *   `AuthContext.jsx`: (Optional) A React Context to manage user authentication state globally.
*   **`services/`**
    *   `firebase.js`: Initializes Firebase and provides access to Firebase services.
    *   `giftIdeaService.js`: Contains functions for fetching, creating, updating, and deleting gift ideas in Firebase.
    *   `userService.js`: Contains functions for fetching user data from Firebase.

## Getting Started

1.  **Clone the repository:**

    ```bash
    git clone <repository-url>
    ```

2.  **Install dependencies:**

    ```bash
    npm install  # or yarn install
    ```

3.  **Configure Firebase:**

    *   Create a Firebase project in the Firebase Console.
    *   Enable Google Authentication.
    *   Set up a Realtime Database.
    *   Copy your Firebase configuration to `src/firebase-config.js`.

4.  **Run the application:**

    ```bash
    npm start  # or yarn start
    ```