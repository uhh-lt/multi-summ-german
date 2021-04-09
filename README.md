# Error Analysis of using BART for Multi-Document Summarization: A Study for English and German Language

Authors: Timo Johner, Abhik Jana, Chris Biemann

Paper: [Link](Link)  

Accepted at the 23rd Nordic Conference on Computational Linguistics ([NoDaLiDa 2021](https://nodalida2021.github.io/)), held from May 31st to June 2nd, 2021. 
Published in the NEALT Proceedings Series by [Linköping University Electronic Press](Link) and in the [ACL Anthology](Link).

This repository describes the implementation of our approach proposed in the paper. 

## Dataset:

name | language | topics | type | paper | source |
-----| -------- | ------ | ----------------- | ---------------- | --------- |
 CNN/DailyMail    | en       | 311,971  |  single-document    | [Link](https://papers.nips.cc/paper/2015/file/afdec7005cc9f14302cd0474fd0f3c96-Paper.pdf)            | retrieved from [here](https://github.com/abisee/cnn-dailymail) 
 Multi-News    | en       | 56,216  |  multi-document         | [Link](https://www.aclweb.org/anthology/P19-1102.pdf)          | adaption for BART by [Hokamp et al (2020)](https://github.com/chrishokamp/dynamic-transformer-ensembles)
 auto-*h*MDS    | de       | 2,100 |  multi-document          | [Link](https://www.aclweb.org/anthology/L18-1510.pdf)          | not publicly available, can be reproduced [here](https://github.com/AIPHES/auto-hMDS)


## Checkpoint: 




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
