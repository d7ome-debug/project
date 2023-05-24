# project
coursera project
import requests

def translate_text(text):
    url = "https://translate.googleapis.com/translate_a/single?client=gtx&sl=fr&tl=en&dt=t&q=" + text
    response = requests.get(url)
    if response.status_code == 200:
        result = response.json()[0][0][0]
        return result
    else:
        return "Error: Something went wrong."

text = "Bonjour comment allez-vous?"
translated = translate_text(text)

print(translated)
