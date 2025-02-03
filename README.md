# PopReel - TikTok Clone

PopReel is a full-stack web application inspired by TikTok, where users can create, share, and discover short-form video content. The platform includes features like video uploading, liking, commenting, sharing, and a smart recommendation system to personalize the user experience.

## Features

- **User Authentication**: Secure user onboarding and authentication using Clerk.
- **Video Upload**: Users can upload short-form videos with minimal latency.
- **Video Feed**: A personalized feed of videos powered by a recommendation system.
- **Interactions**: Users can like, comment, share, and favorite videos.
- **Content Moderation**: A moderation system to prevent inappropriate content from being uploaded.
- **Adaptive Recommendations**: The recommendation system adapts based on the user's most recent activity.
- **Optimized Video Playback**: Smooth video playback with Next.js video optimization techniques.

## Technologies Used

- **Frontend**: Next.js, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: PostgreSQL (for user data and video metadata)
- **Authentication**: Clerk
- **Machine Learning**: Python (for recommendation system)
- **Video Storage**: Cloud storage (e.g., AWS S3, Cloudinary)
- **Deployment**: Vercel (Frontend), Render/Heroku (Backend)

## Project Structure

```
popreel/
├── client/               # Frontend (Next.js)
│   ├── components/       # Reusable components
│   ├── pages/            # Application pages
│   ├── styles/           # CSS/Tailwind styles
│   ├── utils/            # Utility functions
│   └── ...               # Other Next.js files
├── server/               # Backend (Node.js/Express)
│   ├── controllers/      # Route handlers
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── middleware/       # Middleware (e.g., moderation)
│   └── ...               # Other backend files
├── ml/                   # Machine Learning (Recommendation System)
│   ├── data/             # Training data
│   ├── models/           # Trained models
│   └── ...               # Other ML files
├── README.md             # Project documentation
└── ...                   # Other project files
```

## Setup Instructions

### Prerequisites

- Node.js (v18 or higher)
- PostgreSQL
- Python (for ML)
- Clerk account (for authentication)
- Cloud storage account (e.g., AWS S3, Cloudinary)

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/popreel.git
   cd popreel
   ```

2. **Set Up Environment Variables**
   - Create a `.env` file in the `client` and `server` directories.
   - Add the following variables:
     ```
     # Client .env
     NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your-clerk-publishable-key
     NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
     NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
     NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/feed
     NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/feed

     # Server .env
     DATABASE_URL=your-postgres-database-url
     CLOUDINARY_CLOUD_NAME=your-cloudinary-cloud-name
     CLOUDINARY_API_KEY=your-cloudinary-api-key
     CLOUDINARY_API_SECRET=your-cloudinary-api-secret
     ```

3. **Install Dependencies**
   - Frontend:
     ```bash
     cd client
     npm install
     ```
   - Backend:
     ```bash
     cd server
     npm install
     ```
   - Machine Learning:
     ```bash
     cd ml
     pip install -r requirements.txt
     ```

4. **Run Migrations**
   - Set up the PostgreSQL database and run migrations:
     ```bash
     cd server
     npx prisma migrate dev --name init
     ```

5. **Start the Application**
   - Frontend:
     ```bash
     cd client
     npm run dev
     ```
   - Backend:
     ```bash
     cd server
     npm start
     ```

6. **Train the Recommendation System**
   - Navigate to the `ml` directory and run the training script:
     ```bash
     cd ml
     python train_model.py
     ```

7. **Access the Application**
   - Open your browser and navigate to `http://localhost:3000`.

## Challenges and Solutions

1. **Content Moderation**:
   - Implemented a moderation system using AI-based content filtering (e.g., Google Cloud Vision API) to detect inappropriate content during upload.

2. **Adaptive Recommendations**:
   - Built a recommendation system using collaborative filtering and user activity data to personalize the video feed.

3. **Video Optimization**:
   - Used Next.js image and video optimization techniques to ensure smooth playback and minimal latency.

## Future Improvements

- Add real-time notifications for likes, comments, and shares.
- Implement a "For You" page with advanced recommendation algorithms.
- Introduce video editing tools for users.
- Add support for live streaming.
