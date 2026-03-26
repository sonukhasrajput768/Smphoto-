# import requests

# आपकी DeepAI की चाबी (Key)
api_key = '354403a5-4617-4612-a37a-0c199c9b02fc'

# फोटो को बेहतर (Enhance) करने का फंक्शन
def enhance_my_photo(image_path):
    response = requests.post(
        "https://api.deepai.org/api/torch-srgan", # यह HD करने वाला मॉडल है
        files={
            'image': open(image_path, 'rb'),
        },
        headers={'api-key': api_key}
    )
    
    # रिजल्ट में आपको एक लिंक मिलेगा जहाँ फोटो HD हो चुकी होगी
    result = response.json()
    print("HD फोटो का लिंक यहाँ है:", result['output_url'])

# इस्तेमाल करने के लिए:
# enhance_my_photo('your_blurry_photo.jpg')
