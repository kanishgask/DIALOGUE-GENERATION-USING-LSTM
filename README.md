# DIALOGUE-GENERATION-USING-LSTM
🤖 Dialogue Generation using LSTM with Attention
This project implements a simple Seq2Seq chatbot using LSTM with attention mechanism in TensorFlow/Keras. It takes an input sentence and generates a human-like response using a trained sequence-to-sequence model.

**📋 Features**
Encoder-Decoder architecture using LSTM

Implements Bahdanau-style attention using Keras Attention layer

Supports anti-repetition in generated output

Allows temperature-controlled sampling for varied responses

Simple training on toy data; can be extended to larger datasets

**🛠️ Requirements**
Python 3.x

TensorFlow 2.x

NumPy

**Install required packages using:**

bash
Copy
Edit
pip install tensorflow numpy
**📁 Project Structure**
bash
Copy
Edit
dialogue_bot_lstm/
│
├── chatbot.py               # Main training and inference script
├── data/                    # Folder to store training data (if extended)
└── README.md                # This documentation
**🚀 How it Works**
1. Data Preparation
Simple pairs of input → target responses are defined.

Target responses are wrapped with <start> and <end> tokens.

Tokenization is applied to convert text to integer sequences.

Sequences are padded to uniform length.

**2. Model Architecture**
Encoder: Embedding + LSTM

Decoder: Embedding + LSTM

Attention Layer: Computes context vector using encoder outputs and decoder outputs

Final output is passed through a Dense layer with softmax for vocabulary prediction.

**3. Training**
Model is trained using sparse_categorical_crossentropy.

Epochs and batch size are customizable.

The decoder target output is reshaped for Keras' expected format.

**4. Inference**
The encoder outputs are used as context for the decoder.

Decoder generates one word at a time until <end> is reached.

Temperature sampling is used for more diverse and creative outputs.

**💬 Example Usage**
Testing the Bot
python
Copy
Edit
test_inputs = [
    "hello",
    "how are you",
    "what is your name",
    "bye",
    "tell me a joke",
    "what can you do",
    "good night"
]

for sentence in test_inputs:
    print("Input:", sentence)
    print("Bot  :", generate_response(sentence, temperature=0.8))
    print('-' * 30)
**Sample Output**
markdown
Copy
Edit
Input: hello
Bot  : hi
------------------------------
Input: how are you
Bot  : i am fine
------------------------------
Input: what is your name
Bot  : i am a bot
------------------------------
**🎯 Customization**
You can extend this project by:

Adding more training pairs to improve response quality

Replacing the attention layer with a custom implementation

Saving/loading trained models

Integrating into a Flask or web app for deployment

**⚠️ Limitations**
The training dataset is very small (toy data)

Does not handle OOV (Out of Vocabulary) words well

No beam search decoding (greedy decoding only)

Not suitable for production use without further training on large datasets

**📚 References**
TensorFlow Keras Documentation

Sequence to Sequence Learning with Neural Networks

Neural Machine Translation by Jointly Learning to Align and Translate (Bahdanau Attention)

**📄 License**
This project is provided under the MIT License.

**Output:**
<img width="456" height="381" alt="image" src="https://github.com/user-attachments/assets/1b31eb93-b3c9-4cdd-bc6b-6e442f783a27" />


