# RAG using Function calling for tabular data ingestion

This notebook covers how to use the Chat Completions API in combination with external functions to extend the capabilities of GPT models.

`tools` is an optional parameter in the Chat Completion API which can be used to provide function specifications. The purpose of this is to enable models to generate function arguments which adhere to the provided specifications. Note that the API will not actually execute any function calls. It is up to developers to execute function calls using model outputs.

Within the `tools` parameter, if the `functions` parameter is provided then by default the model will decide when it is appropriate to use one of the functions. The API can be forced to use a specific function by setting the `tool_choice` parameter to `{"name": "<insert-function-name>"}`. The API can also be forced to not use any function by setting the `tool_choice` parameter to `"none"`. If a function is used, the output will contain `"finish_reason": "function_call"` in the response, as well as a `tool_choice` object that has the name of the function and the generated function arguments.

## Note: This notebook uses the OpenAI API version 1.0, which was released in Nov 2023. 

### Overview

This notebook contains the following 2 sections:

- **How to generate function arguments:** Specify a set of functions and use the API to generate function arguments.
- **How to call functions with model generated arguments:** Close the loop by actually executing functions with model generated arguments.

- #### Files:
  1. planogramdesign_openai_function_calling.ipynb contains the source code in python
  2. sales_info.json contains the market data that we provide to the LLM, when it asks for data
  3. notebook_output.txt contains sample output from the notebook that can be compared against yours after you run the notebook.
  4. requirements.txt has the libraries and versions used by the notbook code
     
