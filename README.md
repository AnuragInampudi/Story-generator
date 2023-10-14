# Story-generator

google colab notebook: https://colab.research.google.com/drive/1Vb_hg8tskpho7gTJlPdPl67NZJAbhqHM?usp=sharing


Authors: Aishwarya Mathala, Anurag Inampudi


Overview:

This GitHub repository hosts the code for a story generator that uses the GPT-2 language model fine-tuned for generating creative stories in various genres. This powerful tool can be used to generate engaging narratives based on user-defined prompts, making it an excellent resource for creative writing, story ideas, or simply exploring the capabilities of text generation models.

Key Features:

Story Generation: The code leverages Hugging Face's Transformers library to generate stories based on user-specified prompts and genres.
Genre Customization: You can specify the genre for your story, allowing you to create narratives in various styles such as superhero, sci-fi, horror, thriller, action, and drama.
Fine-Tuning: The model is fine-tuned to produce contextually relevant and coherent stories in the selected genre.
Prompt Flexibility: Users can provide input prompts to guide the story generation process, making it adaptable for different creative needs.
Interactive Usage: The repository includes code to interactively generate and display stories within a Jupyter Notebook or Colab environment.

Getting Started;


To use this story generator, you can follow these steps:
Clone the Repository: Clone this GitHub repository to your local machine.
Install Dependencies: Ensure you have the required libraries installed by running the following command in your terminal:
 !pip install transformers torch	 
Generate Stories: Use the provided code to generate stories. You can specify your own prompts and genres.
Customization: If you want to fine-tune the model for specific genres or purposes, you can do so by following the fine-tuning procedures in the code.

Example
Here's a brief example of how to use the story generator:


checkpoint = "pranavpsv/gpt2-genre-story-generator"
model = GPT2LMHeadModel.from_pretrained(checkpoint)
tokenizer = AutoTokenizer.from_pretrained(checkpoint)
story_generator = TextGenerationPipeline(model=model, tokenizer=tokenizer)

input_prompt = "<BOS> <sci_fi> aliens invaded earth"
story = story_generator(input_prompt, min_length=200, max_length=300, min_new_tokens=120, do_sample=True,
           repetition_penalty=1.1, temperature=1.2,
           top_p=0.95, top_k=50)
print(story)

Contributions:
Contributions to this repository are welcome. Feel free to create pull requests or issues if you have ideas for improvements, new features, or bug fixes.

Acknowledgements:
This project is built upon the Hugging Face Transformers library. Special thanks to the contributors and the open-source community.

