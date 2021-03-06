This implementation is based on the [dynet 1.0 library](https://github.com/clab/dynet) for this software to function. The paper is  "Attention Modeling for Targeted Sentiment".

#### Building

    mkdir build
    cd build
    cmake .. -DEIGEN3_INCLUDE_DIR=/path/to/eigen
    make    

### Training and Testing
The training command is
    
    ./attention_context_gated -T [training data] -d [development data] --test_data [test data] --pretrained [pretrained word embeddings] --lexicon sentiment140.lex --report_i 500 --dev_report_i 10 --dynet-mem 1024 --training_methods 1

The test command is

    ./attention_context_gated -T [training data] -d [development data] --test_data [test data] --pretrained [pretrained word embeddings] --lexicon sentiment140.lex --report_i 500 --dev_report_i 10 --dynet-mem 1024 --train_methods 1 --count_limit 1000 --test --model [trained model]

Noted that the sentiment140.lex is imported, but not used, in order to ensure the consistent of the word indexes in the trained model. The trained model is provided in model/model.bz2. You need to uncompress it first, and use it as the trained model.

### Citation
    @InProceedings{liu-zhang:2017:EACLshort,
         author    = {Liu, Jiangming  and  Zhang, Yue},
         title     = {Attention Modeling for Targeted Sentiment},
         booktitle = {Proceedings of the 15th Conference of the European Chapter of the Association for Computational Linguistics: Volume 2, Short Papers},
         month     = {April},
         year      = {2017},
         address   = {Valencia, Spain},
         publisher = {Association for Computational Linguistics},
         pages     = {572--577},
         url       = {http://www.aclweb.org/anthology/E17-2091}
         }

