# Pricing for AI

### Introduction

Understanding tokens is important for effective API usage. Tokens are small pieces of words that the API processes. Knowing how tokens work can help you manage input length and control costs, as pricing is often based on the number of tokens used.

## What are tokens? <a href="#h_4ae02e0c88" id="h_4ae02e0c88"></a>

Tokens can be thought of as pieces of words. Before the API processes the request, the input is broken down into tokens. These tokens are not cut up exactly where the words start or end - tokens can include trailing spaces and even sub-words. Here are some helpful rules of thumb for understanding tokens in terms of lengths:

* 1 token \~= 4 chars in English
* 1 token \~= ¾ words
* 100 tokens \~= 75 words

Or

* 1-2 sentence \~= 30 tokens
* 1 paragraph \~= 100 tokens
* 1,500 words \~= 2048 tokens

To get additional context on how tokens stack up, consider this:

* Wayne Gretzky’s quote "_You miss 100% of the shots you don't take_" contains 11 tokens.
* OpenAI’s [charter](https://openai.com/charter/) contains 476 tokens.
* The transcript of the US _Declaration of Independence_ contains 1,695 tokens.

How words are split into tokens is also language-dependent. For example ‘Cómo estás’ (‘_How are you_’ in Spanish) contains 5 tokens (for 10 chars). The higher token-to-char ratio can make it more expensive to implement the API for languages other than English.

To further explore tokenization, you can use our interactive [Tokenizer tool](https://platform.openai.com/tokenizer), which allows you to calculate the number of tokens and see how text is broken into tokens. Please note that the exact tokenization process varies between models. Newer models like GPT-3.5 and GPT-4 use a different tokenizer than previous models, and will produce different tokens for the same input text.\
​\
Alternatively, if you'd like to tokenize text programmatically, use [Tiktoken](https://github.com/openai/tiktoken) as a fast BPE tokenizer specifically used for OpenAI models.

## Token Limits <a href="#h_051eb08805" id="h_051eb08805"></a>

Depending on the [model](https://beta.openai.com/docs/engines/gpt-3) used, requests can use up to 128,000 tokens shared between prompt and completion. Some models, like **GPT-4 omni** (which we are going to use), have different limits on input and output tokens.

There are often creative ways to solve problems within the limit, e.g. condensing your prompt, breaking the text into smaller pieces, etc.

## Token Pricing <a href="#h_4f7e925c57" id="h_4f7e925c57"></a>

The API offers multiple model types at different price points. Requests to different models are priced differently. You can find details on token pricing [here](https://openai.com/pricing).

| Model             | Pricing (Per 1M Input Tokens) | Pricing (Per 1M Output Tokens) |
| ----------------- | ----------------------------- | ------------------------------ |
| **gpt-4o**        | $5.00                         | $15.00                         |
| gpt-4o-2024-08-06 | $2.50                         | $10.00                         |
| gpt-4o-2024-05-13 | $5.00                         | $15.00                         |

By understanding token limits and costs, you can better manage your usage and budget. [OpenAI Pricing Page](https://openai.com/pricing)

The cost of using the OpenAI API varies depending on the model you choose. The pricing is typically determined per 1,000 tokens, with more advanced models generally costing more. Details of the pricing structure can be found on the [Pricing Overview](https://openai.com/pricing).

## Exploring tokens <a href="#h_cd01d4bb9a" id="h_cd01d4bb9a"></a>

The API treats words according to their context in the corpus data. Models take the prompt, convert the input into a list of tokens, processes the prompt, and convert the predicted tokens back to the words we see in the response.

What might appear as two identical words to us may be generated into different tokens depending on how they are structured within the text. Consider how the API generates token values for the word ‘_red_’ based on its context within the text:

[![](https://openai.intercom-attachments-7.com/i/o/338216191/4e307d0bafbd18f842bd6398/v\_Sp27FQeadYK4lYgk8CA\_l2mR70v-WSOUyXfjjpPj\_Ny9Dc8RRWnxon4o\_ct59dqOgPY\_5D88puOFdquuKueWRsD8sM9DSB7yBntE3KqnrMPhHR91BHClTFTnab3u6i7p051PF4?expires=1723714200\&signature=7ea2a06abe119a1ae8208760b41c9a586537b13a31d3d70f6f8dd9513b13ce84)](https://openai.intercom-attachments-7.com/i/o/338216191/4e307d0bafbd18f842bd6398/v\_Sp27FQeadYK4lYgk8CA\_l2mR70v-WSOUyXfjjpPj\_Ny9Dc8RRWnxon4o\_ct59dqOgPY\_5D88puOFdquuKueWRsD8sM9DSB7yBntE3KqnrMPhHR91BHClTFTnab3u6i7p051PF4?expires=1723714200\&signature=7ea2a06abe119a1ae8208760b41c9a586537b13a31d3d70f6f8dd9513b13ce84)[![](https://openai.intercom-attachments-7.com/i/o/338216193/b54fce4d5b63bdd6fad53f1a/\_Q6XzFgIIAIDmUVdCFHF1vGyic8hG61Pc-3eOIAtOG29qBxEgXsUzCOm\_k2xIn2UfrV9PPCIBuz6YOcPYru\_ssvFZymE8ijKKxxHNEZd8Wx-BwimhfXXNipF6TXm2-Xy3grlXYwO?expires=1723714200\&signature=1cfd10e8eccafdd1a3f8fb0798e40cb77fbdd0343c4bed53618dade950277e10)](https://openai.intercom-attachments-7.com/i/o/338216193/b54fce4d5b63bdd6fad53f1a/\_Q6XzFgIIAIDmUVdCFHF1vGyic8hG61Pc-3eOIAtOG29qBxEgXsUzCOm\_k2xIn2UfrV9PPCIBuz6YOcPYru\_ssvFZymE8ijKKxxHNEZd8Wx-BwimhfXXNipF6TXm2-Xy3grlXYwO?expires=1723714200\&signature=1cfd10e8eccafdd1a3f8fb0798e40cb77fbdd0343c4bed53618dade950277e10)

In the first example above the token “2266” for ‘ red’ includes a trailing space (Note, these are example token ID's for demonstration purposes).

[![](https://openai.intercom-attachments-7.com/i/o/338216196/ed6e3be8fe0db30a33e87555/vvmePo3aWbhExL36QLsDYXe8OaeFvzeqEj4zqXqRGV-5xFA6W8zXu1QQMvsMlycoje4OJPCuA1YMLpokaAvaVH\_CXzWuZInVhCE4wByMEiakQ9HObxECfbo36pKASPtKndcxgPd-?expires=1723714200\&signature=4e10312da58081b11aff29d2579f9e2ac02bdd9a396ed0a643024d7d8cd5970b)](https://openai.intercom-attachments-7.com/i/o/338216196/ed6e3be8fe0db30a33e87555/vvmePo3aWbhExL36QLsDYXe8OaeFvzeqEj4zqXqRGV-5xFA6W8zXu1QQMvsMlycoje4OJPCuA1YMLpokaAvaVH\_CXzWuZInVhCE4wByMEiakQ9HObxECfbo36pKASPtKndcxgPd-?expires=1723714200\&signature=4e10312da58081b11aff29d2579f9e2ac02bdd9a396ed0a643024d7d8cd5970b)[![](https://openai.intercom-attachments-7.com/i/o/338216199/2b15ca3d4d001150fbfff37d/lRvNrEim9UIXmL5j6ahrf2Mcb46uTyMyoL66xygd2GYFJeP4o0DjyBg2B3lIXnZhd1GuWnqIQWJDJ7yrjSzX8JCNMnJ24BJ\_Yfy5CLqbFny6Kns4kVIA2ofPhDBq\_AYVyhU2ELrx?expires=1723714200\&signature=b41b88b894b7cfe946cb23569603c4fc74aa2bfe05280faffd3904df88dfcb9c)](https://openai.intercom-attachments-7.com/i/o/338216199/2b15ca3d4d001150fbfff37d/lRvNrEim9UIXmL5j6ahrf2Mcb46uTyMyoL66xygd2GYFJeP4o0DjyBg2B3lIXnZhd1GuWnqIQWJDJ7yrjSzX8JCNMnJ24BJ\_Yfy5CLqbFny6Kns4kVIA2ofPhDBq\_AYVyhU2ELrx?expires=1723714200\&signature=b41b88b894b7cfe946cb23569603c4fc74aa2bfe05280faffd3904df88dfcb9c)

The token “2296” for ‘ Red’ (with a leading space and starting with a capital letter) is different from the token “2266” for ‘ red’ with a lowercase letter.

[![](https://openai.intercom-attachments-7.com/i/o/338216200/2d91432dfaeceb293e6ede20/4P-Lfk9pc5SwjUw0PqcOrCmT2Tyo1KE86v\_xseULCBSbqXA7k2JVEvFMD3ZVu7PxAq0zFf1xV74r3eoou2RONtvZnxAQjHYig1iXYK98up5c-c1lJrMn-N9uxkCHl3MU3ilc8TTa?expires=1723714200\&signature=6efd4501ff6755906acc060d6259d4be591ecc79df5be2c0ad7c45778949bcb8)](https://openai.intercom-attachments-7.com/i/o/338216200/2d91432dfaeceb293e6ede20/4P-Lfk9pc5SwjUw0PqcOrCmT2Tyo1KE86v\_xseULCBSbqXA7k2JVEvFMD3ZVu7PxAq0zFf1xV74r3eoou2RONtvZnxAQjHYig1iXYK98up5c-c1lJrMn-N9uxkCHl3MU3ilc8TTa?expires=1723714200\&signature=6efd4501ff6755906acc060d6259d4be591ecc79df5be2c0ad7c45778949bcb8)[![](https://openai.intercom-attachments-7.com/i/o/338216202/3481dde46b5529218ef737ab/tWm5ZRDcO4XniG3GnopnJ1lvrKoCxU75Pea3H2Qd8MyGHr-w6Brv4ITnbqpP229XFvz\_7m1zOcJnYR0ZXWXlZAJ0x-XUcWucTa3qmcAy5\_heEK8NXABMIbmshRNiQjdM5qbbGNg0?expires=1723714200\&signature=6584cea2877fed85422d684c3c4e334d96473a7b0ad5ac9f5ed8cb43ae80d869)](https://openai.intercom-attachments-7.com/i/o/338216202/3481dde46b5529218ef737ab/tWm5ZRDcO4XniG3GnopnJ1lvrKoCxU75Pea3H2Qd8MyGHr-w6Brv4ITnbqpP229XFvz\_7m1zOcJnYR0ZXWXlZAJ0x-XUcWucTa3qmcAy5\_heEK8NXABMIbmshRNiQjdM5qbbGNg0?expires=1723714200\&signature=6584cea2877fed85422d684c3c4e334d96473a7b0ad5ac9f5ed8cb43ae80d869)

When ‘Red’ is used in the beginning of a sentence, the generated token does not include a leading space. The token “7738” is different from the previous two examples of the word.

### Observations: <a href="#h_34f2b50bab" id="h_34f2b50bab"></a>

The more probable/frequent a token is, the lower the token number assigned to it:

* The token generated for the period is the same (“13”) in all 3 sentences. This is because, contextually, the period is used pretty similarly throughout the corpus data.
* The token generated for ‘red’ varies depending on its placement within the sentence:
  * Lowercase in the middle of a sentence: ‘ red’ - (token: “2266”)
  * Uppercase in the middle of a sentence: ‘ Red’ - (token: “2297”)
  * Uppercase at the beginning of a sentence: ‘Red’ - (token: “7738”)

### **Token System Overview**

The DDS AI-powered reporting system utilizes advanced AI models that process data in units called "tokens." A token can represent a word, a number, or a punctuation mark. The number of tokens processed directly influences the computational resources required and, therefore, the cost of using the system.

**2. Pricing Structure**

DDS offers a transparent, token-based pricing model for the AI-powered reporting system.

**A. Base Fee**

* A monthly base fee covers the core system infrastructure, data storage, and reporting dashboard access.

**B. Token Usage**

* **Token Consumption:** Tokens are consumed for each report generated. The token count depends on:
  * **Prompt Complexity:** More complex reporting requests (e.g., multi-dimensional analysis, custom filters) will consume more tokens.
  * **Data Volume:** Larger datasets will generally consume more tokens.
  * **AI Model Selection:** Different AI models have different token requirements based on their complexity.
* **Token Bundles:** DDS offers tiered token bundles to cater to different dealership needs and reporting volumes.
  * **Example Tiers:**
    * **Basic:** 5,000 tokens per month.
    * **Standard:** 10,000 tokens per month.
    * **Premium:** 20,000 tokens per month.

**C. Overage Charges**

* If a dealership exceeds their allocated token bundle in a given month, overage charges will apply per additional token consumed.

**3. Example Pricing**

| Tier     | Monthly Base Fee | Token Bundle | Overage Charge (per token) |
| -------- | ---------------- | ------------ | -------------------------- |
| Basic    | $500             | 5,000        | $0.02                      |
| Standard | $800             | 10,000       | $0.015                     |
| Premium  | $1,200           | 20,000       | $0.01                      |

**4. Token Usage Estimation and Optimization**

* **Estimation Tool:** DDS will provide a tool to help dealerships estimate their monthly token consumption based on their typical reporting needs and data volume.
* **Optimization Strategies:** DDS will work with dealerships to optimize token usage by:
  * **Designing efficient prompts:** Crafting concise and focused reporting requests.
  * **Data Aggregation:** Pre-aggregating data within the AI-Ready Data Store to reduce the data volume processed by the AI models.
  * **Model Selection:** Choosing AI models that balance performance with token efficiency.

**5. Benefits of Token-Based Pricing**

* **Transparency:** Dealerships have a clear understanding of their reporting costs.
* **Flexibility:** Dealerships can choose the tier that best suits their needs and adjust their bundle as their reporting requirements change.
* **Cost Control:** By optimizing token usage, dealerships can control their monthly reporting expenses.

**This token-based pricing model offers a transparent and flexible structure, allowing DDS dealerships to leverage AI-powered reporting in a cost-effective manner.**

{% hint style="danger" %}
&#x20;**Note:** This pricing model is illustrative. Final pricing will be determined based on specific dealership requirements and negotiated agreements.
{% endhint %}
