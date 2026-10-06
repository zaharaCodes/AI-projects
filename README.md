# AI Projects

Hands-on AI engineering projects that run **entirely in the browser**: a neural network written from scratch, a CNN image classifier, a RAG chatbot and an LLM agent. Each project is a single HTML file, so there is nothing to install.

**Live demos:** click a project below. Each opens in your browser.

| # | Project | What it shows | Live demo |
|---|---------|---------------|-----------|
| 1 | **Neural Forge** | Neural network built from scratch: forward pass, backpropagation, SGD/Adam, L2 regularization, softmax | [Open](https://zaharacodes.github.io/AI-projects/neural_forge.html) |
| 2 | **Digit Recognizer** | The same network trained on real MNIST digits, then recognizes digits you draw | [Open](https://zaharacodes.github.io/AI-projects/digit_recognizer.html) |
| 3 | **Image Classifier** | Pretrained CNN (MobileNet) classifying uploaded images, plus teach-your-own classes | [Open](https://zaharacodes.github.io/AI-projects/image_classifier.html) |
| 4 | **Live Image Classifier** | Real-time webcam classification with transfer learning | [Open](https://zaharacodes.github.io/AI-projects/image_classifier_live.html) |
| 5 | **Chat with your PDF** | Retrieval-Augmented Generation (RAG) with page citations | [Open](https://zaharacodes.github.io/AI-projects/chat_with_pdf.html) |
| 6 | **AI Agent** | Tool-using LLM agent with a visible think, act, observe loop | [Open](https://zaharacodes.github.io/AI-projects/aiagent.html) |

---

## 1. Neural Forge (`neural_forge.html`)

An interactive playground where you can watch a neural network learn.

- Written from scratch in JavaScript, with **no ML libraries**
- Backpropagation with **SGD** or **Adam**, and an **L2 regularization** slider
- Binary and **3-class (softmax)** classification
- Choose input features (x, y, x², y², xy, sin x, sin y)
- **Train/test split**: hollow dots are test data, so you can see overfitting
- Live decision boundary, loss graph and network diagram
- Save and load trained weights as JSON

## 2. Digit Recognizer (`digit_recognizer.html`)

Trains a from-scratch network (784 → 64 → 10) on the real **MNIST** dataset in your browser, then recognizes digits you draw.

- Reports accuracy on 1,000 test images the network never trained on
- Drawn digits are scaled to 20x20 and centered by center of mass in 28x28, the same way MNIST images are made
- Settings at the top of the script (hidden size, epochs, learning rate) are easy to experiment with

## 3 and 4. Image Classifiers (`image_classifier.html`, `image_classifier_live.html`)

Transfer learning with **TensorFlow.js** and **MobileNet** (a CNN).

- Classifies images into 1000 everyday categories
- **Teach your own classes**: add a few photos (or hold a button to record webcam frames) and it learns them using MobileNet embeddings and a KNN classifier, with no retraining of the CNN
- The live version classifies the webcam feed continuously

## 5. Chat with your PDF (`chat_with_pdf.html`)

A complete **RAG pipeline** running client-side:

1. Extract text with PDF.js
2. Split into overlapping chunks (about 110 words, 25-word overlap)
3. Turn every chunk into an embedding (Universal Sentence Encoder)
4. Find the closest chunks to your question using cosine similarity
5. Optionally send only those chunks to Claude to write a grounded answer

Every answer can show the exact chunks, page numbers and similarity scores it used. Works without an API key (shows the best matching passage).

## 6. AI Agent (`aiagent.html`)

An **agent loop**: the model thinks, picks a tool, the tool runs, the result goes back to the model, and this repeats until it can answer.

- Tools: calculator, current time, random number, save/list notes
- Tool schemas, a step limit and input validation
- Live trace of every thought, action and observation
- Works with the Claude API, or with a rule-based demo brain when no key is provided

---

## Run locally

1. Download or clone this repository.
2. In VS Code, install the **Live Server** extension, right-click any `.html` file and choose **Open with Live Server**.
3. Internet is needed to load TensorFlow.js, PDF.js and the models from CDNs.

The webcam needs `http://localhost` (Live Server) or `https` (the GitHub Pages links above).

## API keys

The Chat with PDF and AI Agent pages have an **optional** Anthropic API key box. The key is only used in your browser tab, and it is never saved or stored in the code. Never commit an API key to this repository.

## Tech

JavaScript, HTML5 Canvas, TensorFlow.js, MobileNet, KNN classifier, Universal Sentence Encoder, PDF.js, Claude API (tool use).

## Author

**Fathima Zahara**: [GitHub](https://github.com/zaharaCodes) | [LinkedIn](https://linkedin.com/in/fathima-zahara525)
