# ChatGPT-Prompt-Experiments
Results of testing multiple ways of prompting chatgpt.

## Tested System Prompts:
- You are a programmer whose job it is to finish the functions provided by the user.
- You're job is to write the functions asked of you by the user.
- You are a language model whose job it is to produce the full function that fulfills the prompt.
## Tested User Prompts (the {} indicate where the function prompt is placed):
- Write the function for me that fulfills the prompt: {}
- Please write the entire function that matches {}
- Please provide a unique solution that complete the function that starts with {}
- I have a function prompt ```{}```\n Please produce the function for me which completes this prompt.
## Not officially tested prompts, but already experimented with:
- Asking chatgpt for code with no explanation can make it produce just code, but it is fairly unreliable and will lead to inconsistent results which can lead to errors introduced through user mistakes.
- Asking chatgpt to intuit the language being tested can sometimes distract it from actually producing any code.
