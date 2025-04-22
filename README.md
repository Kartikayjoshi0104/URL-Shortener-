📎 URL Shortener
A simple and efficient URL shortening service built with Node.js, Express.js, and MongoDB. This application allows users to generate shortened URLs that redirect to the original links.

🚀 Features
Shorten URLs: Convert long URLs into concise, shareable links.

Redirection: Accessing the shortened URL redirects to the original URL.

Persistent Storage: All URLs are stored in MongoDB for persistence.

Validation: Ensures that only valid URLs are shortened.

🛠 Technologies Used
Node.js

Express.js

MongoDB

Mongoose

shortid

valid-url

dotenv

📁 Project Structure
bash
Copy
Edit
url-shortener/
├── models/
│   └── Url.js
├── .env
├── server.js
└── README.md
⚙ Installation and Setup
Clone the repository:

bash
Copy
Edit
git clone https://github.com/yourusername/url-shortener.git
cd url-shortener
Install dependencies:

bash
Copy
Edit
npm install
Configure environment variables:

Create a .env file in the root directory and add the following:

env
Copy
Edit
MONGO_URI=your_mongodb_connection_string
BASE_URL=http://localhost:5000
PORT=5000
Replace your_mongodb_connection_string with your actual MongoDB connection string. If you're using MongoDB Atlas, it would look something like:

env
Copy
Edit
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/urlShortener?retryWrites=true&w=majority
Start the server:

bash
Copy
Edit
node server.js
The server will start on the port specified in the .env file (default is 5000).

📬 API Endpoints
1. Shorten a URL
Endpoint: POST /shorten

Description: Shortens a given URL.

Request Body:

json
Copy
Edit
{
  "originalUrl": "https://www.example.com"
}
Response:

json
Copy
Edit
{
  "_id": "unique_id",
  "originalUrl": "https://www.example.com",
  "shortUrl": "http://localhost:5000/shortid",
  "urlCode": "shortid",
  "date": "timestamp"
}
2. Redirect to Original URL
Endpoint: GET /:code

Description: Redirects to the original URL associated with the given code.

Example: Accessing http://localhost:5000/shortid will redirect to https://www.example.com.

🧪 Testing the API
You can use tools like Postman or cURL to test the API endpoints.

Example using cURL:

bash
Copy
Edit
curl -X POST http://localhost:5000/shorten \
     -H 'Content-Type: application/json' \
     -d '{"originalUrl": "https://www.example.com"}'
📄 License
This project is licensed under the MIT License.

🙌 Acknowledgments
Inspired by the need for a simple URL shortening service.

Thanks to the developers of the open-source packages used in this project.
