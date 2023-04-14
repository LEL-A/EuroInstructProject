# 🇪🇺 💬 EuroInstructProject
This project generates instruction datasets from existing German,
English and other European open source datasets.

Through fine-tuning this should then help to add instruction-following capabilities
to GPT models. To learn more about it please see our
[documentation page](https://github.com/LEL-A/doc).

## Instruct GermanDPR Dataset v1 (German)
This dataset is derived from the [GermanDPR](https://www.deepset.ai/germanquad)
dataset from [deepset.ai](https://www.deepset.ai/).
Many thanks to you!

To learn more about the base data set see the arXiv paper:
[GermanQuAD and GermanDPR: Improving Non-English Question Answering and Passage Retrieval](https://arxiv.org/abs/2104.12741)

The record has three columns: `input`, `output` and `uuid`

The `input` of the record set always consists of a text block and a question about this text block.
If the question can be answered with the help of the text block,
then the `output` contains exactly this text passage.
If the answer is not contained in the text block,
then this is also communicated in the output.
The number of positive responses and the number of negative responses are exactly balanced.
The column `uuid` contains a uuid generated with `uuid.uuid4()`.

- `InstructGermanDPR_v1.ipynb`: script to generate this dataset
- `instruct_data/InstructGermanDPR_v1_train.csv`: 18,541 train pairs of input and output
- `instruct_data/InstructGermanDPR_v1_test.csv`: 2,050 test pairs of input and output

The dataset can be loaded with:
```python
df_train = pd.read_csv("./instruct_data/InstructGermanDPR_v1_train.csv")
df_train = pd.read_csv("./instruct_data/InstructGermanDPR_v1_test.csv")
```

## Instruct OPUS Tatoeba v1 (English and German)
This dataset is derived from the [Tatoeba v2022-03-03](https://opus.nlpl.eu/Tatoeba-v2022-03-03.php)
dataset. The prompt asks to provide a translation.

The record has five columns: `input`, `output`, `src_lang`, `target_lang` and `uuid`

The `input` of the record provides a German or English text and asks in German or English
text to translate it.
The `output` contains exactly (and only) the translated text.
`src_lang` and `target_lang` contains the language from which is translated into the other.
The column `uuid` contains a uuid generated with `uuid.uuid4()`.

- `Instruct_OPUS_Tatoeba_v1.ipynb`: script to generate this dataset
- `Instruct_OPUS_Tatoeba_v2022_03_03_de_en_v1.csv.gz`: 626,254 pairs of input and output

The dataset can be loaded with:
```python
df = pd.read_csv("./instruct_data/Instruct_OPUS_Tatoeba_v2022_03_03_de_en_v1.csv.gz")
```

## Licensing (Datasets)
The code and documentation of this project are under MIT license.
The licenses of the datasets are stated below.

### Instruct GermanDPR
`InstructGermanDPR` is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
It is derived from the [GermanDPR](https://www.deepset.ai/germanquad)
dataset from [deepset.ai](https://www.deepset.ai/).
Many thanks to you!

With the help of `InstructGermanDPR_v1.ipynb` changes were made.
Please also see the arXiv paper:
[GermanQuAD and GermanDPR: Improving Non-English Question Answering and Passage Retrieval](https://arxiv.org/abs/2104.12741)

### Tatoeba v2022-03-03
Tatoeba v2022-03-03 is licensed under [CC BY 2.0 FR](https://creativecommons.org/licenses/by/2.0/fr/).

- citation: J. Tiedemann, 2012, [Parallel Data, Tools and Interfaces in OPUS](https://opus.nlpl.eu/Tatoeba-v2022-03-03.php). In Proceedings of the 8th International Conference on Language Resources and Evaluation (LREC 2012)
- copyright: https://tatoeba.org/eng/terms_of_use

## Licensing (Code and Documentation)
Copyright (c) 2023 by the LEL-A team

Licensed under the **MIT License** (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License by reviewing the file
[LICENSE](https://raw.githubusercontent.com/LEL-A/EuroInstructProject/main/LICENSE) in the repository.
