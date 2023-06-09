# ChatGPT-Prompt-Experiments
Results of testing multiple ways of prompting chatgpt.

## Extraction Methodology:
To Extract the code from ChatGPT, I do the following steps
1. Identify the first code block in the response. If there is no code block the entire message is considered to be code.
2. Extract everything after the first line indented by atleast 2 spaces. I am assuming this is after a function declaration which should not be indented.
3. If it is d, add an opening bracket, if it is java, cpp, cs, rs, scala, sh, or swift, remove the final closing bracket

### Known Issues:
- Java sometimes has the behavior of returning a class around the function. This causes the processing to fail as it is not extracting just function code. Possible solutions could be to add extra processing behavior to handle this.
- The indentation idea seems promising, but could break if there is a new language that doesn't follow any indentation rules. It is the most fragile part of the code so far.

## Tested System Prompts:
- You are a programmer whose job it is to finish the functions provided by the user.
- Your job is to write the functions asked of you by the user.
- You are a language model whose job it is to produce the full function that fulfills the prompt.
- Your job is to write just the functions asked of you by the user. Write only the function.
- Your job is to write the complete function that completes the given function prompt. Write the entire function from function declaration to the return statement and closing bracket.
## Tested User Prompts (the {} indicate where the function prompt is placed):
- Write the function for me that fulfills the prompt: {}
- Please write the entire function that matches {}
- Please provide a unique solution that complete the function that starts with {}
- I have a function prompt \`\`\`{}\`\`\`\n Please produce the function for me which completes this prompt.
- I want to test your ability to write a function. I have a function defintion and signature: \`\`\`{}\`\`\`\n Please write the function including the function declaration, return statement, and closing bracket that fulfills this function prompt.
## Not officially tested prompts, but already experimented with:
- Asking chatgpt for code with no explanation can make it produce just code, but it is fairly unreliable and will lead to inconsistent results which can lead to errors introduced through processing the response.
- Asking chatgpt to intuit the language being tested can sometimes distract it from actually producing any code.
## Observations
- Combination of the system prompt 3 and user prompt 3 seems to be the best and give what is expected so far.
