# Number Classification API

This project is a Flask-based API that classifies a given number based on various properties such as whether it is prime, perfect, Armstrong, odd, or even. It also provides a fun fact about the number if it is an Armstrong number. Accepts GET requests with a number parameter, returns JSON in the specified format, handles edge cases gracefully (non-numeric inputs, negative numbers, numbers with multiple properties), and provides appropriate HTTP status codes.


## Features

- Classifies a number as prime, perfect, Armstrong, odd, or even.
- Provides the sum of the digits of the number.
- Returns a fun fact if the number is an Armstrong number.

## Endpoints

### GET `/api/classify-number`

#### Query Parameters

- `number` (required): The number to classify.

#### Responses

##### 200 OK

```json
{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "class_sum": 11,
    "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
}
```
##### 400 Bad Response

```json
{
    "number": "alphabet",
    "error": true
}
```

## Setup

### 1. Clone the repository
```markdown
git clone https://github.com/LNCH92/Number-classification-API.git
cd your-repository
```
### 2. Create a virtual environment and activate it:
```markdown
python -m venv .venv
source .venv\Scripts\activate
```
### 3. Install the required packages:
```markdown
pip install -r requirements.txt
```

### 4. Run the Flask application
```markdown
python classify-api.py
```
### 5. Open your browser and navigate to the link below to test the endpoint.
``` markdown
http://127.0.0.1:5000/api/classify-number?number=371
```
## Deployment to AWS Elastic Compute Cloud (EC2)
### 1. SSH to a runnung instance on AWS
```markdown
ssh -i your-key.pem ubuntu@ec2-public-IPV4-DNS.amazonaws.com
```
### 2. Update and install dependencies
```markdown
sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip -y
```
### 3. Create and activate a virtual environment
```markdown
python3 -m venv myenv
source myenv/bin/activate
```
### 4. Install Flask and gunicorn
```markdown
pip install Flask
pip install gunicorn
```
### 5. Clone the git repository
```markdown
git clone https://github.com/LNCH92/Number-classification-API.git
```
### 6. Run your API using gunicorn on port 5000
```markdown
gunicorn --bind 0.0.0.0:5000 classify-api:app
```
### 7. Create an inbound rule allowing *custom TCP* on *port 5000*
Enter AWS server > Security group > inbound rule > edit rules > save rules
### 8. Open web browser and navigate to this link
```markdown
http://ec2-user-public-IP-address:5000/api/classify-number?number=371
```
Enter your AWS EC2 public-IP address where applicable.

## Dependencies
1. Flask
2. Flask-Marshmallow

## MIT License 



