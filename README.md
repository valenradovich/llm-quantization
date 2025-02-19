# LLMs quantization

## introduction
these days LLMs are HUGE (i mean they are called large language models, otherwise they would be small language models) and we always need to fit them in small memory to run on less powerful devices.

when weights are learned during training or fine-tuning, they are stored as numerical values like fp32 or fp16. the larger the data type, the more accurate the models are. combining this with the natural improvement that models have when they increase the training data and parameters, we conclude that they are getting bigger and bigger.

to store and infer these LLMs weights and parameters, we have a high cost of memory if stored as fp32 or fp16.

the purpose of quantization is to use fewer bits (rescale values) to store these parameters while minimizing loss of accuracy. for example, fp16 to int4, int2, int1 representation. with this technique, we can run large models on smaller GPUs, CPUs, and even on mobile devices, making them more accessible for a wider range of applications.

even though we try to minimize the degradation in model performance, we'll still have some because we are literally **losing mathematical precision** in our operations.

## some tests
<ins>gemma2-9b 1-bit quantized:</ins>

![1-bit-chat](https://github.com/valenradovich/llm-quantization/assets/86897297/dc3b04a7-4ced-460f-81ef-e0dce9897af0)


<ins>gemma2-9b 4-bit quantized:</ins>

![4-bit-chat](https://github.com/valenradovich/llm-quantization/assets/86897297/e015949b-de40-47b3-a536-14c1e306f351)

## usage
the notebook in the repo is ready-to-go using Google Colab.
