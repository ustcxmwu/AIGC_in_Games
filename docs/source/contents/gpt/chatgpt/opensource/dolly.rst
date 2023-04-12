.. _Dolly:

Dolly
================================================================================

1. 安装

.. code:: bash

    git clone https://github.com/databrickslabs/dolly.git
    
2. 下载模型, 模型地址: `databricks/dolly-v1-6b <https://huggingface.co/databricks/dolly-v1-6b/tree/main>`_


3. 运行文件, dolly 本身没有带推理文件, 需要自己写

.. code:: python

    import numpy as np
    from transformers import (
                AutoModelForCausalLM,
                AutoTokenizer,
                PreTrainedModel,
                PreTrainedTokenizer)
    import torch
    
    tokenizer = AutoTokenizer.from_pretrained("./dolly-v1-6b", padding_side="left")
    model = AutoModelForCausalLM.from_pretrained("./dolly-v1-6b", device_map="auto", trust_remote_code=True, torch_dtype=torch.float16)
    
    
    
    PROMPT_FORMAT = """Below is an instruction that describes a task. Write a response that appropriately completes the request.
    
    ### Instruction:
    {instruction}
    
    ### Response:
    """
    
    def generate_response(instruction: str, *, model: PreTrainedModel, tokenizer: PreTrainedTokenizer, 
                          do_sample: bool = True, max_new_tokens: int = 256, top_p: float = 0.92, top_k: int = 0, **kwargs) -> str:
        input_ids = tokenizer(PROMPT_FORMAT.format(instruction=instruction), return_tensors="pt").input_ids.to("cuda")
    
        # each of these is encoded to a single token
        response_key_token_id = tokenizer.encode("### Response:")[0]
        end_key_token_id = tokenizer.encode("### End")[0]
    
        gen_tokens = model.generate(input_ids, pad_token_id=tokenizer.pad_token_id, eos_token_id=end_key_token_id,
                                    do_sample=do_sample, max_new_tokens=max_new_tokens, top_p=top_p, top_k=top_k, **kwargs)[0].cpu()
    
        # find where the response begins
        response_positions = np.where(gen_tokens == response_key_token_id)[0]
    
        if len(response_positions) >= 0:
            response_pos = response_positions[0]
            
            # find where the response ends
            end_pos = None
            end_positions = np.where(gen_tokens == end_key_token_id)[0]
            if len(end_positions) > 0:
                end_pos = end_positions[0]
    
            return tokenizer.decode(gen_tokens[response_pos + 1 : end_pos]).strip()
    
        return None
    
    # Sample similar to: "Excited to announce the release of Dolly, a powerful new language model from Databricks! #AI #Databricks"
    if __name__ == "__main__":
        output = generate_response("美国现任总统是谁", model=model, tokenizer=tokenizer)
       print(output)


dolly 回答受模型所限制

.. code:: bash

    $ python generate.py
    Barack Obama is the current President of the United States.

