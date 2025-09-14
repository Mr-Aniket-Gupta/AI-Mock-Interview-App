# AI Mock Interview - Environment Setup Guide

## 📋 Prerequisites
Before setting up the environment variables, make sure you have:
- Node.js installed
- Git installed
- A code editor (VS Code recommended)

## 🔧 Step-by-Step Environment Setup

### Step 1: Create .env.local File
1. Navigate to your project root directory (`ai-mock-interview`)
2. Create a new file named `.env.local`
3. Copy the environment variables from this guide into the file

### Step 2: Database Setup (Neon PostgreSQL)

#### 2.1 Create Neon Account
1. Go to [https://console.neon.tech/](https://console.neon.tech/)
2. Sign up for a free account
3. Create a new project
4. Choose a region close to your location

#### 2.2 Get Database Connection String
1. In your Neon dashboard, go to "Connection Details"
2. Copy the connection string
3. Add it to your `.env.local` file:

```env
# Database Configuration
NEXT_PUBLIC_DRIZZLE_DB_URL='postgresql://neondb_owner:npg_sd0NYh9qOlLH@ep-restless-salad-ads7rzdp-pooler.c-2.us-east-1.aws.neon.tech/neondb?sslmode=require&channel_binding=require'
```

### Step 3: Authentication Setup (Clerk)

#### 3.1 Create Clerk Account
1. Go to [https://dashboard.clerk.com/](https://dashboard.clerk.com/)
2. Sign up for a free account
3. Create a new application
4. Choose "Next.js" as your framework

#### 3.2 Get Clerk Keys
1. In your Clerk dashboard, go to "API Keys"
2. Copy the Publishable Key and Secret Key
3. Add them to your `.env.local` file:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_Y2hvaWNlLXBlZ2FzdXMtOTMuY2xlcmsuYWNjb3VudHMuZGV2JA
CLERK_SECRET_KEY=sk_test_BI9boZD0E0BBrcIox2zBePJxWRchmdJBf7wp8YsboX
```

### Step 4: AI Integration (Google Gemini)

#### 4.1 Create Gemini API Key
1. Go to [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the generated API key

#### 4.2 Add Gemini API Key
Add the API key to your `.env.local` file:

```env
# Google Gemini AI
NEXT_PUBLIC_GEMINI_API_KEY=AIzaSyDZazv-YMviYAxwhAlqviIpPN_ibVKqbHs
```

### Step 5: Next.js Configuration

#### 5.1 Add NextAuth Configuration
Add these variables to your `.env.local` file:

```env
# Next.js Configuration
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_nextauth_secret_here
```

**Note:** Replace `your_nextauth_secret_here` with a random string. You can generate one using:
```bash
openssl rand -base64 32
```

## 📁 Complete .env.local File Template

```env
# Database Configuration
NEXT_PUBLIC_DRIZZLE_DB_URL='postgresql://neondb_owner:npg_sd0NYh9qOlLH@ep-restless-salad-ads7rzdp-pooler.c-2.us-east-1.aws.neon.tech/neondb?sslmode=require&channel_binding=require'

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_Y2hvaWNlLXBlZ2FzdXMtOTMuY2xlcmsuYWNjb3VudHMuZGV2JA
CLERK_SECRET_KEY=sk_test_BI9boZD0E0BBrcIox2zBePJxWRchmdJBf7wp8YsboX

# Google Gemini AI
NEXT_PUBLIC_GEMINI_API_KEY=AIzaSyDZazv-YMviYAxwhAlqviIpPN_ibVKqbHs

# Next.js Configuration
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_nextauth_secret_here
```

## 🚀 Final Steps

### 1. Install Dependencies
```bash
npm install
```

### 2. Setup Database
```bash
npm run db:push
```

### 3. Start Development Server
```bash
npm run dev
```

### 4. Open Application
Visit [http://localhost:3000](http://localhost:3000) in your browser

## ⚠️ Important Notes

- **Never commit `.env.local` to version control**
- **Keep your API keys secure and private**
- **Use different keys for development and production**
- **Regularly rotate your API keys for security**

## 🔍 Troubleshooting

### Common Issues:
1. **Database Connection Error**: Check if your Neon database URL is correct
2. **Authentication Issues**: Verify Clerk keys are properly set
3. **AI Not Working**: Ensure Gemini API key is valid and has proper permissions
4. **Build Errors**: Make sure all environment variables are set correctly

### Getting Help:
- Check the console for error messages
- Verify all environment variables are properly formatted
- Ensure all services (Neon, Clerk, Gemini) are active and accessible

'
#Get this from your Neon dashboard: https://console.neon.tech/

NEXT_PUBLIC_DRIZZLE_DB_URL='postgresql://neondb_owner:npg_sd0NYh9qOlLH@ep-restless-salad-ads7rzdp-pooler.c-2.us-east-1.aws.neon.tech/neondb?sslmode=require&channel_binding=require'

NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_nextauth_secret_here

NEXT_PUBLIC_GEMINI_API_KEY=AIzaSyDZazv-YMviYAxwhAlqviIpPN_ibVKqbHs

NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_Y2hvaWNlLXBlZ2FzdXMtOTMuY2xlcmsuYWNjb3VudHMuZGV2JA
CLERK_SECRET_KEY=sk_test_BI9boZD0E0BBrcIox2zBePJxWRchmdJBf7wp8YsboX
'