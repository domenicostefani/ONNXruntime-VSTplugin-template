# OnnxTemplatePlugin

This is a template plugin for the [ONNX](https://onnx.ai/) framework. It is intended to be used as a starting point for creating new plugins.
  
Crosscompilation has been tested as a headless plugin for the Elk Audio OS on a Raspberry PI4.  
`/libs` includes an onnxruntime (`1.7.0`) binary for linux-aarch64.

Clone with `--recursive` to get the submodule dependencies.

## Instruction for Elk Audio OS

1. Open `OnnxTemplatePlugin.jucer` with the Projucer and save to generate the project files.
2. cd into `Builds/linux-aarch64` and run `compileDebugElkPi4.sh` (Making sure you downloaded the appropriate ElkPiSDK, read the script comments for more info).
3. Copy the generated `Builds/linux-aarch64/build/OnnxTemplatePlugin.vst3` to your Elk Pi4 in the `~/plugins/` folder.
4. Copy `config_onnxtemplate.json`, `add_current_dir_to_LD_LIBRARY_PATH.sh` and `libs/onnxruntime1.7.0-build-linux_aarch64/libonnxruntime.so.1.7.0` to a folder of your choice on the Elk Pi4.
5. From a terminal in the board, run:
    ```
    source add_current_dir_to_LD_LIBRARY_PATH.sh
    sushi -r -c config_onnxtemplate.json
    ``` 