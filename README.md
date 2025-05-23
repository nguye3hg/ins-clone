# Simplified Instagram Clone

A minimal Instagram clone built using **Vite**, **React**, and **Firebase**. This web app simulates core features of Instagram like user authentication, image uploads, profile viewing, and post liking.

---

##  Features

-  Firebase Authentication (Sign In / Sign Up)
-  Post image with caption (Firebase Storage)
-  User profiles with post display
-  Like system (tracked by user UID)
-  Instagram-style dark theme
-  Vite-powered development

---

##  Tech Stack

- **Frontend**: React + Vite
- **Backend/Storage**: Firebase (Auth, Firestore, Storage)
- **Hosting**: Netlify or Firebase Hosting

---

##  Local Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/instagram-clone.git
cd instagram-clone
```
### 2. Install Dependencies 
```bash
npm install
```
### 3. Configure Environment Variables and Firebase
Create a .env file in the root directory with the following content:

```bash
VITE_FIREBASE_API_KEY=AIzaSyB7a-4zzLWZX4DF6D25HszIHpNvh20YBXA
VITE_FIREBASE_AUTH_DOMAIN=instagram-clone-ea589.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=instagram-clone-ea589
VITE_FIREBASE_STORAGE_BUCKET=instagram-clone-ea589.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=704365087411
VITE_FIREBASE_APP_ID=1:704365087411:web:4bf098ab62c836a953fec6
VITE_FIREBASE_MEASUREMENT_ID=G-5S448SD7RN
```
###  Firestore Structure

#### Collection: `users`

- `uid`: string  
- `displayName`: string  
- `email`: string  
- `photoURL`: string

#### Collection: `posts`

- `caption`: string  
- `createdAt`: timestamp  
- `createdBy`: user UID  
- `imageURL`: Firebase Storage URL  
- `likes`: array of user UIDs

---

### Firebase Storage Rules
```
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```
### 4. Start Development Server
```bash
npm run dev
```
