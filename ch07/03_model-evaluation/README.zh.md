# 第 7 章：根据指令进行微调

此文件夹包含可用于模型评估的实用程序代码。

&nbsp;
## 使用 OpenAI API 评估指令响应

- [llm-instruction-eval-openai.ipynb](llm-instruction-eval-openai.zh.ipynb) 笔记本使用 OpenAI 的 GPT-4 评估指令微调模型生成的响应。它使用以下格式的 JSON 文件：

```python
{
    "instruction": "What is the atomic number of helium?",
    "input": "",
    "output": "The atomic number of helium is 2.",               # <-- The target given in the test set
    "model 1 response": "\nThe atomic number of helium is 2.0.", # <-- Response by an LLM
    "model 2 response": "\nThe atomic number of helium is 3."    # <-- Response by a 2nd LLM
},
```

&nbsp;
## 使用 Ollama 在本地评估指令响应

- [llm-instruction-eval-ollama.ipynb](llm-instruction-eval-ollama.zh.ipynb) 笔记本提供了上述笔记本的替代方案，它利用通过 Ollama 本地下载的 Llama 3 模型。