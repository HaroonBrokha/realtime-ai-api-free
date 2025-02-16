# Realtime AI Search Engine API - Public Documentation

Welcome to the **Realtime AI Search Engine API**. This API provides users with advanced AI-powered insights based on web data retrieved from search engine results. The system fetches the top search results, extracts visible content, and combines it with AI knowledge to generate detailed analysis.

The API is designed to help users get professional, detailed, and insightful responses to their queries by combining web-sourced data with AI-driven knowledge. It ensures the information is not just scraped but deeply analyzed and presented in a single cohesive response.

## Key Features
- **Real-Time Data**: Fetches and processes live search engine results.
- **AI-Powered Responses**: Merges search data with advanced AI insights to provide comprehensive and professional analysis.
- **Customizable Queries**: Users can input any query, and the API returns relevant, updated results along with AI insights.
- **Flexible Integration**: Suitable for integrating into various applications for real-time search analysis.
- **Error Handling**: Includes detailed error messages for different failure scenarios, ensuring smooth integration.

## How It Works

### 1. User Inputs Query:
   A user provides a query (for example, "today gaming news").

### 2. Top 3 Search Results:
   The API fetches the top 3 search results from Google Search using a third-party service.

### 3. Content Extraction:
   The visible text from these search results is extracted using Cheerio, a popular web scraping library. This data serves as the base for the AI analysis.

### 4. AI Integration:
   The extracted content from the top search results is combined with the AI system’s existing knowledge. This integrated data is then processed to generate detailed insights.

### 5. AI Response:
   Finally, the AI generates a well-structured, detailed, and professional response, providing the user with a comprehensive answer based on both the search results and the AI's insights.

By using this API, you will always have access to the latest insights, driven by real-time web data and advanced AI capabilities.

## **API Endpoint**

### **Endpoint:**
```
https://ai-search-engine-api.vercel.app/api/search?searchFor={query}&hlgamingApi={api}
```

### **Parameters:**

- **searchFor** (`required`): A search query (string) for which you want AI-powered analysis (e.g., "today gaming news").
- **hlgamingApi** (`required`): The API key (string) that authenticates your request. This key is necessary for accessing the API.

#### **Example Request:**

```plaintext
https://ai-search-engine-api.vercel.app/api/search?searchFor=today%20gaming%20news&hlgamingApi={api}
```
## **Getting the API Key**

To use the API, you need to obtain an API key. Follow these steps:

### **Register for an API Key:**
- Visit the official [API Key Registration Page](https://www.hlgamingofficial.com/p/api.html).
- Sign up for an account and obtain your unique API key.

### **Using the API Key:**
In your requests, replace `{api}` with the API key you obtained. Example:

```plaintext
&hlgamingApi={api}
```
## **Response Format**

The API returns a **JSON** response with the following structure:

- **success**: A boolean indicating whether the request was successful.
- **query**: The original search query.
- **analysis**: The AI-generated response that combines content from web results with additional insights from the AI model.

### **Example Response:**

```json
{
  "success": true,
  "query": "today gaming news",
  "analysis": "Today, the gaming industry is experiencing a surge in new releases and updates. Key trends include VR/AR integration, esports growth, and a focus on mobile gaming... [AI Insights & Relevant External Data]."
}
```
# Real-Time AI Search Engine API

## **Error Handling**

If the API encounters an issue, it will return a relevant error code and message. Here are the possible errors:

### **1. Missing `searchFor` Parameter**

If the `searchFor` parameter is missing, the API will return:

```json
{
  "error": "Missing searchFor parameter."
}
```
### **2. Invalid API Key**

If the `hlgamingApi` parameter is invalid or missing, the API will return:

```json
{
  "error": "Invalid API key. Get it from https://www.hlgamingofficial.com/p/api.html"
}
```
### **3. Timeout or Network Errors**

If the API takes too long to respond or encounters a network issue, it may return:

```json
{
  "error": "Internal server error"
}
```
### **How It Works**

Here’s a breakdown of how the API processes requests:

1. **User Inputs Query**: A user provides a search query (e.g., "today gaming news").
2. **Top 3 Search Results**: The API fetches the top 3 search results from Google Search using a third-party service.
3. **Content Extraction**: The visible text from these search results is extracted using Cheerio (a web scraping library).
4. **AI Integration**: The content from these top results is fed into an AI system that combines the external data with its own knowledge.
5. **AI Response**: The AI generates a detailed, professional single-paragraph response and returns it to the user.

### **Example Request and Response**

#### Request Example:

To search for gaming news today, send a GET request like this:

```plaintext
GET https://ai-search-engine-api.vercel.app/api/search?searchFor=today%20gaming%20news&hlgamingApi={api}
```
### **Response Example:**

If successful, the API will return a JSON response like this:

```json
{
  "success": true,
  "query": "today gaming news",
  "analysis": "The gaming world is buzzing today with new updates in VR technology, the rise of esports, and the expansion of mobile games. Game developers are focusing on immersive experiences, leveraging augmented reality and virtual reality for an even more engaging experience..."
}
```
