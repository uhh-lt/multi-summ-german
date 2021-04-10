# Error Analysis of using BART for Multi-Document Summarization: A Study for English and German Language

Authors: Timo Johner, Abhik Jana, Chris Biemann

Paper: [Link](Link)  

Accepted at the 23rd Nordic Conference on Computational Linguistics ([NoDaLiDa 2021](https://nodalida2021.github.io/)), held from May 31st to June 2nd, 2021. 
Published in the NEALT Proceedings Series by [Linköping University Electronic Press](Link) and in the [ACL Anthology](Link).

This repository describes the implementation of our approach proposed in the paper. 

## Datasets:

name | language | topics | type | paper | source |
-----| -------- | ------ | ----------------- | ---------------- | --------- |
 CNN/DailyMail    | en       | 311,971  |  single-document    | [Link](https://papers.nips.cc/paper/2015/file/afdec7005cc9f14302cd0474fd0f3c96-Paper.pdf)            | retrieved from [here](https://github.com/abisee/cnn-dailymail) 
 Multi-News    | en       | 56,216  |  multi-document         | [Link](https://www.aclweb.org/anthology/P19-1102.pdf)          | adaption for BART by [Hokamp et al (2020)](https://github.com/chrishokamp/dynamic-transformer-ensembles)
 auto-*h*MDS    | de       | 2,100 |  multi-document          | [Link](https://www.aclweb.org/anthology/L18-1510.pdf)          | not publicly available, can be reproduced [here](https://github.com/AIPHES/auto-hMDS)


## Setup:

The checkpoint for the fine-tuned BART model on the German auto-*h*MDS dataset can be downloaded [here](Link). The checkpoint file can be used to reproduce our results with the following setup. 

### Fine-Tuning: 

We used the BART model based on the fairseq library. More information can be found [here](https://github.com/pytorch/fairseq/blob/master/examples/bart/README.md).  

For fine-tuning on the three datasets (see above) we used the following parameters:


```
  CUDA_VISIBLE_DEVICES=1 fairseq-train hMDS_2-bin \
    --restore-file bart.large/model.pt \
    --max-tokens 1024 \
    --task translation \
    --source-lang source --target-lang target \
    --truncate-source \
    --layernorm-embedding \
    --share-all-embeddings \
    --share-decoder-input-output-embed \
    --reset-optimizer --reset-dataloader --reset-meters \
    --required-batch-size-multiple 1 \
    --arch bart_large \
    --criterion label_smoothed_cross_entropy \
    --label-smoothing 0.1 \
    --dropout 0.1 --attention-dropout 0.1 \
    --weight-decay 0.01 --optimizer adam --adam-betas "(0.9, 0.999)" --adam-eps 1e-08 \
    --clip-norm 0.1 \
    --lr-scheduler polynomial_decay --lr 3e-05 \
    --update-freq 1  \
    --skip-invalid-size-inputs-valid-test \
    --find-unused-parameters;

```



## Citation:
If you find this paper interesting, please cite: 

```
@inproceedings{#add,
    title = "Error Analysis of using BART for Multi-Document Summarization: A Study for English and German Language",
    author = "Johner, Timo and
    Abhik, Jana and
    Chris Biemann
    booktitle = "#add",
    month = #add,
    year = "2021",
    address = "Online",
    publisher = "#add",
    url = "#add",
    pages = "#add",
}
```
