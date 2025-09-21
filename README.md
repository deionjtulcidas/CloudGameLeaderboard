
## Features
- **Frontend**: Responsive HTML/CSS/JS site hosted on Amazon S3 (static website hosting).
  **Backend**: Serverless APIs powered by Amazon API Gateway + AWS Lambda.
  **Database**: Amazon DynamoDB for storing and retrieving player scores.
  **Real-time**: Scores update instantly using WebSocket APIs and broadcast Lambda functions.
  **CORS Configured**: Fully working browser-to-API requests.

---

## Architecture
1. **Frontend** hosted on S3 → connects to API Gateway.  
2. **API Gateway** routes requests to Lambda functions.  
3. **Lambda** functions handle `POST /scores` (write to DynamoDB) and `GET /leaderboard` (query top scores).  
4. **DynamoDB Streams + Broadcast Lambda** push updates via WebSocket API.  

---

## Problems I Overcame
- **API Gateway not resolving**: Had to reconfigure stages (`$default`) and redeploy routes properly.  
- **"Not Found" errors**: Solved by verifying stage + route integration with Lambda.  
- **CORS issues in browser**: Fixed by correctly setting `Access-Control-Allow-Origin`, `Content-Type` headers, and redeploying.  
- **Lambda debugging**: Used CloudWatch logs to trace incoming events and validate JSON parsing.  

This process showed how critical **deployment stages**, **CORS**, and **integration requests** are when building cloud-native apps.

---

## How to Use
2. Submit a score using your name and value.  
3. Watch the leaderboard update with new entries in real time.

---

## Skills Demonstrated
- AWS Lambda  
- Amazon API Gateway (HTTP + WebSocket APIs)  
- Amazon DynamoDB (+ Streams)  
- Amazon S3 (static hosting)  
- CloudWatch monitoring/logs  
- Debugging CORS and deployment issues  
