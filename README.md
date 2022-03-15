# Directed Network Embedding with Virtual Negative Edges
This repository provides a reference implementation of *DIVINE* as described in the following paper:
> Directed Network Embedding with Virtual Negative Edges<br>
> Hyunsik Yoo, Yeon-Chang Lee, Kijung Shin, and Sang-Wook Kim<br>
> 15th ACM Int'l Conf. on Web Search and Data Mining (WSDM 2022)<br>

<!-- [Online Apendix](https://sites.google.com/view/divine-wsdm22/main-page) -->

### Authors
- Hyunsik Yoo (hsyoo32@hanyang.ac.kr)
- Yeon-Chang Lee (lyc0324@hanyang.ac.kr)
- Kijung Shin (kijungs@kaist.ac.kr)
- Sang-Wook Kim (wook@hanyang.ac.kr)


### Requirements
The code has been tested running under Python 3.5. The required packages are as follows:
- ```scikit-learn==0.21.3 (specific version for STNE)```
- ```numpy```
- ```tqdm```
- ```networkx```
- ```pandas```

#### For WRMF:
- ```tensorflow==1.13.1```
- ```Cython```

go to '*./NeuRec*' and compile the evaluator of cpp implementation with the following command line:
```bash
python setup.py build_ext --inplace
```

#### For STNE:
- ```texttable```

#### For SIDE:
OS: Only Mac OS and Linux are available for this code.
- ```tensorflow==1.1```

##### (Please refer to the author's original README.md for more details of WRMF, STNE, and SIDE.)

### Arguments

```
--vne_algo                Method for inferring degree of negativity
--selection_strategy      Strategey for selcting VNEs
--theta                   Hyperparamter for determining the number of VNEs to be added
--dataset                 Input (unsigned) network
--emb_algo                (Signed) network embedding method for learning node embeddings
--num_embed               Dimensionality of embeddings
--lp_task                 Link prediction task type
```

### Basic Usage

```bash
python divine.py --dataset GNU --emb_algo stne --lp_task LP-uniform --num_embed 128 --vne_algo wrmf --theta 0.5 --selection_strategy local
```

### Cite
We encourage you to cite our paper if you have used the code in your work. You can use the following BibTex citation:
```
@inproceedings{YooLSK22,
  author    = {Hyunsik Yoo and Yeon{-}Chang Lee and Kijung Shin and Sang{-}Wook Kim},
  title     = {Directed Network Embedding with Virtual Negative Edges},
  booktitle = {The Fifteenth ACM International Conference on Web Search and Data Mining (WSDM 2022)},
  pages     = {1291--1299},
  year      = {2022}
}
```
