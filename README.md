# *AGILE*
*AGILE*: A Hierarchical Dataflow Framework for CGRA Mapping


## How to run *AGILE*?

>* Most modules of *AGILE* are written in Python. We test *AGILE* on *anaconda* and *python 3.7*.  

>* Install the dependencies: 
```
conda create -n scip python=3.7
conda activate scip
conda install matplotlib scikit-learn networkx xmltodict scip graphviz pyscipopt cvxpy -c conda-forge
pip install graphviz
```

>* Run the benchmark
```
export SET=express
export BENCH=cosine2
python3 ./test/pnr.py ./benchmark/${SET}/${BENCH}/${BENCH}_DFG.txt ./benchmark/${SET}/${BENCH}/${BENCH}_compat.txt \
        -p ./benchmark/${SET}/${BENCH}/${BENCH}_param.txt 
```
>>* The default mapping parameters will be used if ./test/pnr.py is run without "-p xxx_param.txt ". 

>* Components such as partitioning, DSE, mapping, etc. can be found under `test`.

>* Compilation is optional. It is needed if you want to use the front-end or use the C++ interface. 
>>* You can compile *AGILE* by running "make". The front-end is tested in LLVM 11.  

## Description about the code

>* arch/: code about CGRA modeling
>* benchmark/: CGRA-ME/ExPRESS/standard benchmarks
>* common/: provides basic functions
>* dataflow/: code about dataflow modeling
>* mapping/: code about CGRA mapping (scheduling, placement, routing)
>* test/: code about experiments
>>* test/pnr.py: CGRA mapping
>>* test/dse.py: design space exploration
>>* test/dfgpart.py: dataflow graph partition
