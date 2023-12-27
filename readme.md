#### `data/` directory
- `drug.txt`: list of drug names
- `protein.txt`: list of protein names
- `disease.txt`: list of disease names
- `se.txt`: list of side effect names
- `drug_dict_map`: a complete ID mapping between drug names and DrugBank ID
- `protein_dict_map`: a complete ID mapping between protein names and UniProt ID
- `mat_drug_se.txt` 		: Drug-SideEffect association matrix
- `mat_protein_protein.txt` : Protein-Protein interaction matrix
- `mat_protein_drug.txt` 	: Protein-Drug interaction matrix
- `mat_drug_protein.txt` 	: Drug_Protein interaction matrix (transpose of the above matrix)
- `mat_drug_protein_remove_homo.txt`: Drug_Protein interaction matrix, in which homologous proteins with identity score >40% were excluded (see the paper).
- `mat_drug_drug.txt` 		: Drug-Drug interaction matrix
- `mat_protein_disease.txt` : Protein-Disease association matrix
- `mat_drug_disease.txt` 	: Drug-Disease association matrix
- `Similarity_Matrix_Drugs.txt` 	: Drug similarity scores based on chemical structures of drugs
- `Similarity_Matrix_Proteins.txt` 	: Protein similarity scores based on primary sequences of proteins



### 1. 改变T10中的intra（视角内）对比的子图生成
- 原两个都使用随机dropout，并将所有sim>0.5的置为1，其余置为0的方法；
- 在T10-23-03-26中，使用dropout，并将所有sim>0.5的置为1，其余置为0生成一个子图；
- 使用所有sim>0.5的保留值，其余置为0生成一个子图；

### 2. 在1中更改子图生成方法后，更改GCN层数为2层
- 分别评估只使用第二层GCN的输出和使用两层输出相加的效果

### 3. add shuffle to train and test data (2023-04-03-17:09)
# 0616
```text
已经添加了ddi、ppi的重构损失
1. 使用dot乘法重构dd和pp的相似度网络

1. 添加dti的重构损失


```