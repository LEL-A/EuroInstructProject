# 🇪🇺 💬 EuroInstructProject
This project generates instruction datasets from existing German,
English and other European open source datasets.

Through fine-tuning this should then help to add instruction-following capabilities
to GPT models. To learn more about it please see our
[documentation page](https://github.com/LEL-A/doc).

## InstructGermanDPR Dataset v1
This dataset is derived from the [GermanDPR](https://www.deepset.ai/germanquad)
dataset from [deepset.ai](https://www.deepset.ai/).
Many thanks to you!

To learn more about the base data set see the arXiv paper:
[GermanQuAD and GermanDPR: Improving Non-English Question Answering and Passage Retrieval](https://arxiv.org/abs/2104.12741)

The record following three columns: `input`, `output` and `uuid`

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

## Licensing (Datasets)
The code and documentation of this project are under MIT license.
The licenses of the datasets are stated below.

### InstructGermanDPR
This dataset is licensed under the [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).
It is derived from the [GermanDPR](https://www.deepset.ai/germanquad)
dataset from [deepset.ai](https://www.deepset.ai/).
Many thanks to you!

With the help of `InstructGermanDPR_v1.ipynb` changes were made.
Please also see the arXiv paper:
[GermanQuAD and GermanDPR: Improving Non-English Question Answering and Passage Retrieval](https://arxiv.org/abs/2104.12741)

## Licensing (Code and Documentation)
Copyright (c) 2023 by the LEL-A team

Licensed under the **MIT License** (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License by reviewing the file
[LICENSE](https://raw.githubusercontent.com/LEL-A/EuroInstructProject/main/LICENSE) in the repository.
