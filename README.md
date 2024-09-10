# 🎭 Verse-AI

<div align="center">
	<img src="images/logo.png" height="300">
</div>

<br>

<div align="center">
   <img src="images/made-with-python.svg">
   <!-- <img src="images/built-with-love.svg"> -->
   <br>
   <img src="images/WIP.svg"><img src="images/contribute.svg">
</div>


## 📖 Overview

Verse-AI is an end-to-end Poetry Generation Model that harnesses the power of transformer-based language models and natural language processing to learn the patterns, structure, and vocabulary of poems. By fine-tuning a pre-trained model (FLAN-T5) on a diverse collection of poems from different styles and topics, the model can capture the nuances and characteristics of various poetic forms and intelligently generate poems that adhere to specific themes or topics.

## ➕ Features

- **Data Preparation**: The model uses a custom `PoemDataset` class to prepare the input data, which includes poem topics and the corresponding poems. This dataset class handles tokenization and encoding of the input and target texts.
- **Model Architecture**: Verse-AI utilizes the FLAN-T5 model, a powerful sequence-to-sequence transformer model, as its base architecture. The model is fine-tuned on the poetry dataset to adapt it for poem generation.
- **Training Process**: The model is trained using PyTorch, with support for GPU acceleration when available. It employs the AdamW optimizer and uses a customizable training loop that allows for easy monitoring of the training progress.
- **Evaluation Metrics**: During training, the model calculates and reports various metrics to assess its performance:
  - Perplexity: Measures how well the model predicts the sample.
  - Distinct-n: Evaluates the diversity of the generated text.
  - Repetition Rate: Assesses the model's tendency to repeat phrases.
- **Poem Generation**: Once trained, the model can generate new poems by providing a prompt in the format "Generate a poem about [topic]". The generation process uses beam search and includes parameters to control the output, such as maximum length and n-gram repetition prevention.
- **Evaluation and Fine-tuning**: The generated poems can be evaluated using metrics such as BLEU score, as well as the distinct-n and repetition rate metrics. This evaluation process helps in fine-tuning the model by adjusting hyperparameters and training strategies to optimize the results and enhance the quality and creativity of the generated poems.

## 🌳 Organization

    ├── LICENSE				<- MIT License
    ├── README.md          			<- The top-level README for developers using this project. (you are here!)
    ├── data
    │   ├── processed      			<- The final, canonical data sets for modeling.
    │   └── raw            			<- The original, immutable data dump.
    │
    ├── models             			<- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          			<- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         		   the creator's initials, and a short `-` delimited description, e.g.
    │                         		   `1.0-jqp-initial-data-exploration`.
    │
    ├── reports            			<- Generated analysis as HTML, PDF, LaTeX, etc.
    │
    ├── requirements.txt   			<- The requirements file for reproducing the analysis environment
    │
    └── src                			<- Source code for use in this project.
        ├── data           			<- Scripts to download or generate data
        │   └── make_dataset.py
        │
        ├── features       			<- Scripts to turn raw data into features for modeling
        │   └── build_features.py
        │
        ├── models         			<- Scripts to train models and then use trained models to make
        │   │                 		   predictions
        │   ├── predict_model.py
        │   └── train_model.py
        │
        └── visualization  			<- Scripts to create exploratory and results oriented visualizations
            └── visualize.py

## 🖲️ Installation

To set up Verse-AI, follow the instructions below:

1. Clone the repository:

```bash
git clone https://github.com/yourusername/poetic.git
```

2. Navigate to the project directory:

```bash
cd poetic
```

3. Create a virtual environment (recommended):

   1. For Linux/Mac:

      ```bash
      python3 -m venv venv
      ```
   2. For Windows:

      ```bash
      python -m venv venv
      ```
4. Activate the virtual environment:

   1. For Linux/Mac:

      ```bash
      source venv/bin/activate
      ```
   2. For Windows (for cmd, for powershell replace the .bat with .ps1):

      ```bash
      .\venv\Scripts\activate.bat
      ```
5. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## 💻 Usage

The Poetry Generation Model can be used as follows:

1. Data Preparation:
   - Prepare your poetry dataset with topics and corresponding poems.
   - Implement the `PoemDataset` class as shown in the code.

2. Train the model:
   - Customize the model configuration in the training script.
   - Run the following command:

     ```bash
     python src/models/train_model.py
     ```
   - The trained model will be saved in the `models` directory.

3. Generate Poems:
   - Use the `generate_poem` function to create new poems.
   - Example usage:

     ```python
     prompt = "Generate a poem about love"
     generated_poem = generate_poem(model, tokenizer, prompt)
     print(generated_poem)
     ```

4. Evaluate the model:
   - Use the provided evaluation metrics (perplexity, distinct-n, repetition rate, BLEU score) to assess the quality of the generated poems.
   - Fine-tune the model based on the evaluation results.

## 👨‍👩‍👧‍👦 Contributors

<a href="https://github.com/yourusername/poetic/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=yourusername/poetic" />
</a>

## 💫 Reach Out

<div align="center">
   <table>
      <tbody>
         <tr>
               <td>
                  <a href="https://www.linkedin.com/in/yourusername/">
                     <img height="50" src="https://www.vectorlogo.zone/logos/linkedin/linkedin-icon.svg" >
                  </a>
               </td>
               <td>
                  <a href="https://github.com/yourusername">
                     <img height="50" src="https://upload.vectorlogo.zone/logos/github/images/47bfd2d4-712f-4dee-9315-f99c611b7598.svg" />
                  </a>
               </td>
               <td>
                  <a href="https://discordapp.com/users/yourdiscordid">
                     <img height="50" src="https://www.vectorlogo.zone/logos/discordapp/discordapp-tile.svg"/>
                  </a>
               </td>
         </tr>
      </tbody>
   </table>
</div>

## 📃 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

With Verse-AI, you can embark on a creative journey of generating unique poems that capture the essence of different themes and styles. Let your imagination flow and dive into the world of AI-assisted poetry creation!

Happy poem generation! 📝✨





