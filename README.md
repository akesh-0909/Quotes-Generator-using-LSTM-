# LSTM Quote Generator 📜

[![image](https://github.com/akesh-0909/Quotes-Generator-using-LSTM-/assets/155313882/1d0f225f-f6b4-4f67-8878-aa92aabd9a96)
](https://youtu.be/A6BeG1yf6Jw?si=oWzK_CUsvm4HdbAe)


Generate inspiring quotes using a trained LSTM model, built on a dataset of 1000 quotes from various authors and backgrounds.

## Overview

This project utilizes a Long Short-Term Memory (LSTM) neural network to generate quotes based on patterns learned from a curated dataset. The model was trained using quotes scraped from a website, ensuring diversity in language and style.

## Features ✨

- **Quote Generation**: Input a starting phrase, word  or choose random prompts to generate unique quotes.
- **Web Interface**: Access the model via a user-friendly Gradio interface for easy interaction.
- **API Access**: Integrate quote generation into other applications using the provided API endpoints.

## Usage 🚀

### Web Interface

1. Run the jupyter file then from last cell click on url to redirect to the deployed Gradio interface.
2. Enter a prompt to generate a quote.
3. Explore the generated quotes and their diversity.

   # Example
![Untitled video - Made with Clipchamp (1)](https://github.com/akesh-0909/Quotes-Generator-using-LSTM-/assets/155313882/de3e9a73-2187-4689-a560-c091387861c3)

For more example refer this [video](https://youtu.be/A6BeG1yf6Jw?si=8SPN2DN3bcEz1ZZF)


### API Usage

1. Send a POST request to the API endpoint with a JSON payload containing the prompt.
2. Receive a JSON response with the generated quote.
 

### Example
- **Python**
```python
from gradio_client import Client

client = Client("https://8a60bc40aabf89f175.gradio.live/")
result = client.predict(
		Prompt="Hello!!",
		nwords=13,
		api_name="/predict"
)
print(result)
```
- **JavaScript**
```javascript
import { Client } from "@gradio/client";

const client = await Client.connect("https://8a60bc40aabf89f175.gradio.live/");
const result = await client.predict("/predict", { 		
		Prompt: "Hello!!", 		
		nwords: 10, 
});

console.log(result.data);
```
- **Bash**
```bash
curl -X POST https://8a60bc40aabf89f175.gradio.live/call/predict -s -H "Content-Type: application/json" -d '{
  "data": [
    "Hello!!",
    10
]}' \
  | awk -F'"' '{ print $4}'  \
  | read EVENT_ID; curl -N https://8a60bc40aabf89f175.gradio.live/call/predict/$EVENT_ID
```
**Note :**  Load and run `main.ipynb` and replace links with current active links. Directly goining to links will not work. 


## Contributing 🤝

Contributions are welcome! Please fork the repository and create a pull request with your improvements.

## License 📝

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

[linkedin](linkedin.com/in/akeshkumar)

