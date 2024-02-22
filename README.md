# List of ML File Formats

This repository is a comprehensive list of ML/AI file formats, intended as a resource for tool development and vulnerability research. We aim to keep this list as up-to-date and accurate as possible. If you discover any missing file formats, inaccuracies, or if you have more details to contribute, please raise an issue or submit a pull request.


| Name                                                                                                                                                                                                                 | ML-specific | Framework/Organization (if applicable) | PolyFile/Fickling support | Extensions              | Additional Notes                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------------------------------------- | ------------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| [PyTorch v1.3](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                                      | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: ZIP file containing data.pkl (1 pickle file)                                                                                             |
| [PyTorch v0.1.1](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                                    | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: Tar file with sys_info, pickle, storages, and tensors                                                                                    |
| [PyTorch v0.1.10](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                                   | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: Stacked pickle files                                                                                                                     |
| [TorchScript v1.4](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                                  | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: ZIP file with data.pkl, constants.pkl, and version (2 pickle files and a folder)                                                         |
| [TorchScript v1.3 (deprecated)](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                     | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: ZIP file with data.pkl and constants.pkl (2 pickle files)                                                                                |
| [TorchScript v1.1 (deprecated)](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                     | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: ZIP file with model.json and attribute.pkl (a JSON file and a pickle file)                                                               |
| [TorchScript v1.0 (deprecated)](https://github.com/pytorch/pytorch/issues/31877)                                                                                                                                     | Yes         | PyTorch                                | Yes (Fickling)            | .pt, .pth, .bin         | Description: ZIP file with model.json and constants.pkl (a JSON file and a pickle file)                                                               |
| [PyTorch model archive format [ZIP]](https://github.com/pytorch/serve/tree/master/model-archiver#artifact-details)                                                                                                   | Yes         | PyTorch                                | Yes (Fickling)            | .mar                    | Description: ZIP file that includes Python code files and pickle files                                                                                |
| [PyTorch model archive format [TAR]](https://github.com/pytorch/serve/tree/master/model-archiver#artifact-details)                                                                                                   | Yes         | PyTorch                                | No                        | .mar                    | Description: TAR file that includes Python code files and pickle files                                                                                |
| [PyTorch Package](https://pytorch.org/docs/stable/package.html)                                                                                                                                                      | Yes         | PyTorch                                | No                        | .pt, .pth, .bin         | Description: ZIP file that includes a pickled model, user files represented as a Python package, and framework files including serialized tensor data |
| [ExecuTorch](https://pytorch.org/executorch/main/pte-file-format.html)                                                                                                                                               | Yes         | PyTorch                                | No                        | .pte                    | Description: Modified binary flatbuffer file with optional data segments appended                                                                     |
| [Torch.export](https://pytorch.org/docs/stable/export.html)                                                                                                                                                          | Yes         | PyTorch                                | No                        | .pt2                    | Description: ZIP file with JSON files and Python code file                                                                                            |
| [PyTorch Mobile](https://pytorch.org/tutorials/recipes/mobile_perf.html?highlight=mobile)                                                                                                                            | Yes         | PyTorch                                | No                        | .ptl                    | Description: Modified binary flatbuffer file                                                                                                          |
| [Safetensors](https://github.com/huggingface/safetensors)                                                                                                                                                            | Yes         | Independent                            | In progress (PolyFile)    | .safetensors            | [Refer to our audit](https://github.com/trailofbits/publications/blob/master/reviews/2023-03-eleutherai-huggingface-safetensors-securityreview.pdf)   |
| [ONNX](https://github.com/onnx/onnx)                                                                                                                                                                                 | Yes         | Independent                            | No                        | .onnx                   | [Refer to LobotoMI](https://github.com/alkaet/LobotoMl)                                                                                               |
| [Keras native file format](https://keras.io/guides/serialization_and_saving/#saving)                                                                                                                                 | Yes         | Keras                                  | No                        | .keras                  | Description: ZIP archive with 2 JSON files and 1 h5 file                                                                                              |
| [TensorFlow Saved Models](https://www.tensorflow.org/guide/saved_model)                                                                                                                                              | Yes         | TensorFlow                             | No                        | .pb                     | [Description: Custom Protobuf format. Can result in arbitrary code execution.](https://hiddenlayer.com/research/models-are-code/)                     |
| [TensorFlow Checkpoint](https://www.tensorflow.org/guide/checkpoint)                                                                                                                                                 | Yes         | TensorFlow                             | No                        | .ckpt                   | [Description: Custom Protobuf format. Can result in arbitrary code execution.](https://hiddenlayer.com/research/models-are-code/)                     |
| [TFLite](https://www.tensorflow.org/lite/guide)                                                                                                                                                                      | Yes         | TensorFlow                             | No                        | .tflite                 | Description: Modified binary flatbuffer file                                                                                                          |
| [TFJS](https://www.tensorflow.org/js/guide/save_load)                                                                                                                                                                | Yes         | TensorFlow                             | No                        | \-                      | Description: JSON file and binary file with weights. Technically not a singular file format.                                                          |
| [TF1 Hub format (deprecated)](https://www.tensorflow.org/hub/tf1_hub_module#:~:text=The%20TF1%20Hub%20format%20is%20similar%20to%20the%20SavedModel%20format,different%20tagging%20conventions%20for%20metagraphs).) | Yes         | TensorFlow                             | No                        | \-                      | Description: Custom Protobuf format.                                                                                                                  |
| [Tensorizer](https://github.com/coreweave/tensorizer)                                                                                                                                                                | Yes         | CoreWeave                              | No                        | \-                      | Not uncommon especially in private production systems                                                                                                 |
| [TFRecords](https://www.tensorflow.org/tutorials/load_data/tfrecord)                                                                                                                                                 | Yes         | TensorFlow                             | No                        | .tfrecords              | Description: Wrapper around a Protocol Buffer                                                                                                         |
| [NPY](https://numpy.org/devdocs/reference/generated/numpy.lib.format.html)                                                                                                                                           | Yes         | NumPy                                  | No                        | .npy                    | Used to integrate pickle by default as well.                                                                                                          |
| [NPZ](https://docs.scipy.org/doc/numpy-1.9.3/reference/generated/numpy.savez.html#:~:text=compressed%20.npz%20archive-,The%20.,npy%20format.)                                                                        | Yes         | NumPy                                  | No                        | .npz                    | Description: ZIP file of NPY files                                                                                                                    |
| [GGUF](https://github.com/ggerganov/ggml/blob/master/docs/gguf.md)                                                                                                                                                   | Yes         | llama.cpp/GGML                         | No                        | .gguf                   | \-                                                                                                                                                    |
| [GGML](https://github.com/rustformers/llm/blob/main/crates/ggml/README.md)                                                                                                                                           | Yes         | llama.cpp/GGML                         | No                        | .ggml                   | \-                                                                                                                                                    |
| [GGMF (deprecated)](https://github.com/ggerganov/ggml/blob/master/docs/gguf.md#historical-state-of-affairs)                                                                                                          | Yes         | llama.cpp/GGML                         | No                        | .ggmf                   | \-                                                                                                                                                    |
| [GGJT (deprecated)](https://github.com/ggerganov/ggml/blob/master/docs/gguf.md#historical-state-of-affairs)                                                                                                          | Yes         | llama.cpp/GGML                         | No                        | .ggjt                   | \-                                                                                                                                                    |
| [NetCDF](https://www.unidata.ucar.edu/software/netcdf/)                                                                                                                                                              | Yes         | Independent                            | No                        | .nc                     | \-                                                                                                                                                    |
| [PMML](https://en.wikipedia.org/wiki/Predictive_Model_Markup_Language)                                                                                                                                               | Yes         | Independent                            | No                        | \-                      | \-                                                                                                                                                    |
| [MLeap](https://github.com/combust/mleap)                                                                                                                                                                            | Yes         | Spark                                  | No                        | .mleap                  | \-                                                                                                                                                    |
| [CoreML](https://apple.github.io/coremltools/mlmodel/index.html)                                                                                                                                                     | Yes         | Apple                                  | No                        | .coreml                 | \-                                                                                                                                                    |
| MLFlow Format                                                                                                                                                                                                        | Yes         | MLFlow                                 | No                        | \-                      | \-                                                                                                                                                    |
| MLFlow TensorSpec input format                                                                                                                                                                                       | Yes         | MLFlow                                 | No                        | \-                      | \-                                                                                                                                                    |
| [SurrealML](https://github.com/surrealdb/surrealml)                                                                                                                                                                  | Yes         | SurrealDB                              | No                        | .surml                  | \-                                                                                                                                                    |
| [Llamafile](https://github.com/Mozilla-Ocho/llamafile?tab=readme-ov-file)                                                                                                                                            | Yes         | Independent                            | No                        | .llamafile              | \-                                                                                                                                                    |
| [.prompt](https://docs.humanloop.com/docs/prompt-file-format)                                                                                                                                                        | Yes         | HumanLoop                              | No                        | .prompt                 | \-                                                                                                                                                    |
| [Pickle](https://docs.python.org/3/library/pickle.html)                                                                                                                                                              | No          | Python/Independent                     | Yes                       | .pkl                    | Refer to Fickling                                                                                                                                     |
| Joblib                                                                                                                                                                                                               | No          | Independent                            | Yes                       | \-                      | \-                                                                                                                                                    |
| Nemo                                                                                                                                                                                                                 | Yes         | NVIDIA                                 | No                        | \-                      | \-                                                                                                                                                    |
| Riva                                                                                                                                                                                                                 | Yes         | NVIDIA                                 | No                        | \-                      | \-                                                                                                                                                    |
| AVRO                                                                                                                                                                                                                 | No          | Independent                            | ?                         | \-                      | \-                                                                                                                                                    |
| PARQUET                                                                                                                                                                                                              | No          | Independent                            | ?                         | \-                      | \-                                                                                                                                                    |
| ORC                                                                                                                                                                                                                  | No          | Independent                            | No                        | \-                      | \-                                                                                                                                                    |
| JSON                                                                                                                                                                                                                 | No          | Independent                            | Yes                       | \-                      | \-                                                                                                                                                    |
| CSV                                                                                                                                                                                                                  | No          | Independent                            | ?                         | \-                      | \-                                                                                                                                                    |
| Protocol Buffers                                                                                                                                                                                                     | No          | Independent                            | ?                         | \-                      | Usually an underlying file format                                                                                                                     |
| HDF5                                                                                                                                                                                                                 | No          | Independent                            | No                        | .h5                     | \-                                                                                                                                                    |
| [Caffe](https://caffe.berkeleyvision.org/tutorial/net_layer_blob.html)                                                                                                                                               | Yes         | Caffe                                  | No                        | .caffemodel & .prototxt | Description: Protobuf-based file format                                                                                                               |
| [ArmNN Flatbuffers](https://arm-software.github.io/armnn/20.02/serializers.xhtml#S8_serializer)                                                                                                                      | Yes         | ArmNN                                  | No                        | \-                      | \-                                                                                                                                                    |
| [Cambricon](https://github.com/Cambricon/CNStream)                                                                                                                                                                   | Yes         | Independent                            | No                        | \-                      | \-                                                                                                                                                    |
| [Circle](https://nnfw.readthedocs.io/_/downloads/en/latest/pdf/)                                                                                                                                                     | Yes         | Independent                            | No                        | \-                      | \-                                                                                                                                                    |
| ZIP                                                                                                                                                                                                                  | No          | Independent                            | Yes                       | \-                      | Usually an underlying file format                                                                                                                     |
| [CNTK v1 (deprecated)](https://learn.microsoft.com/en-us/cognitive-toolkit/cntk-library-api)                                                                                                                         | Yes         | Microsoft Cognitive Toolkit            | No                        | \-                      | \-                                                                                                                                                    |
| [CNTK v2](https://learn.microsoft.com/en-us/cognitive-toolkit/cntk-library-api)                                                                                                                                      | Yes         | Microsoft Cognitive Toolkit            | No                        | \-                      | Description: Protobuf-based file format                                                                                                               |
| [Darknet](https://github.com/hank-ai/darknet)                                                                                                                                                                        | Yes         | [Hank.ai](http://hank.ai/) Darknet     | No                        | \-                      | \-                                                                                                                                                    |
| [DL4J](https://deeplearning4j.konduit.ai/v/en-1.0.0-beta7/getting-started/cheat-sheet)                                                                                                                               | Yes         | DL4J                                   | No                        | \-                      | Description: ZIP-based file format                                                                                                                    |
| [Deep Learning Container (DLC)](https://developer.qualcomm.com/software/qualcomm-neural-processing-sdk/learning-resources/developing-apps-with-neural-processing-sdk/working-with-machine-learning)                  | Yes         | Qualcomm Neural Processing SDK         | No                        | .dlc                    | \-                                                                                                                                                    |
