# 🃏 **Playing Cards Classifier with Deep Learning**

A deep learning-based system to classify playing cards (e.g., Ace of Spades, Queen of Hearts, Joker) using computer vision. The model utilizes **EfficientNet-B0** and **InceptionResNetV2**, delivering high-accuracy predictions and is deployed using **Flask** and **Docker** on **AWS EC2**.

🔗 **📸 Demo Video**: [Playing Card Classifier Demo](https://drive.google.com/file/d/1Bfn32NM9u4Tz_i_K1Z09pkDnLOaqcnBx/view?usp=sharing) 
  **Saved Models** : [Link to download the saved models](https://drive.google.com/file/d/1uP-ex8muZtECnyifc2rzltzBKsOYhWm_/view?usp=sharing)

---

## 🚀 **Features**

- 🃏 **Card Classification**: Classifies 53 unique playing cards from image inputs.
- 🤖 **Multi-Model Ensemble**: Combines predictions from EfficientNet-B0 and InceptionResNetV2.
- ⚡ **High Accuracy**: Achieves >90% accuracy in real-world testing.
- 🔁 **Real-Time Inference**: Supports real-time classification via API.
- 📦 **Dockerized**: Easily deployable with Docker.

---

## 🛠️ **Tech Stack**

- **Python 3.8**
- **PyTorch** – deep learning framework
- **Flask** – lightweight API server
- **Docker** – containerization
- **AWS EC2 & ECR** – cloud hosting & container registry

---

## 📦 **Deployment**

### 🚀 Run Locally with Docker

```bash
# Clone the repository and navigate into it
git clone https://github.com/your-username/cards-classifier.git
cd cards-classifier

# Build the Docker image
docker build -t card-classifier .

# Run the Docker container
docker run -p 5002:5002 card-classifier
```

---

## 🔌 **API Usage**

Once the Flask app is running (on http://localhost:5002), you can use the /predict endpoint to classify a card image.

### 📤 POST /predict
Send a POST request with a file using the file field.

🧪 Example using cURL

```bash
curl -X POST -F "file=@path_to_card_image.jpg" http://localhost:5002/predict
```

### Example JSON Response:
```bash
{
  "efficientnet_predictions": [
    {"class": "king of spades", "probability": 0.91},
    {"class": "queen of spades", "probability": 0.03},
    {"class": "jack of hearts", "probability": 0.02}
  ],
  "inception_predictions": [
    {"class": "king of spades", "probability": 0.93},
    {"class": "queen of diamonds", "probability": 0.04},
    {"class": "ace of hearts", "probability": 0.01}
  ]
}
```

