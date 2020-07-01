# bert+crf NER
Although BERT models are powerful, to do NER tasks, CRF layer is still essential. 


## tags
Different from the run_ner.py already in the examples, we regard the tokens that are not at the starting position of a word to have the tag "X", which is in the labels set. E.g., fot the CoNLL03 task, the labels are ["X", "O", "B-MISC", "I-MISC",  "B-PER", "I-PER", "B-ORG", "I-ORG", "B-LOC", "I-LOC"]. 

The code for CRF module comes from AllenNLP. 

## how-to-use
```bash

# run
python transformers1/examples/bert_crf/run_ner_crf.py \
--data_dir ./ \
--labels ./labels.txt \
--model_type bert \
--model_name_or_path bert-base-cased \
--do_train \
--do_eval \
--do_predict \
--per_gpu_train_batch_size 8 \
--per_gpu_eval_batch_size 16 \
--do_lower_case \
--output_dir output \
--overwrite_output_dir \
--overwrite_cache \
--logging_steps 100 \
--save_steps 100 \
--num_train_epochs 20 \
--max_seq_length 128
``` 
