# Knight Online Table Crypto Editor

This tool will allow targeting any version of KnightOnLine executables and change/update continuously their encryption keys. If you are looking into cheats, you are probably in the wrong place, as this tool is meant to be used for people that are into KO development.

Loading the target executable into the tool will parse all the bytes in the binary that have similar pattern for the encryption algorithm, so when it comes to patching, it knows exactly the right offsets to be patched.

For more information, please visit [ko4life.net](https://www.ko4life.net/).

### Getting Started

You can decide whether you want to build this project from source or download the binary from the [releases here](https://github.com/ko4life-net/KO-TBLCryptoEditor/releases).

Your target executable must be unpacked, otherwise it would obviously won't work or find any offsets. To verify this, please download [Detect-It-Easy](http://ntinfo.biz/index.html) and check in the `Entropy` whether the PE is packed.

It is recommended that the target exe you load into this tool, will be in the root directory where the client is, so it would automatically detect the Data folder where the TBLs are and update their encryption to match with the new keys as well, otherwise the file dialog will ask you to select the right path.

Note that if you cannot update Key2, it is because the parser detected that the compiler inlined some of the functions, which made the compiler generate multiple instructions to create the second key dynamically. Therefore, it would only be enabled for executables that do not have inlined functions.

After generating new random keys, click the `Update Client Encryption` button to apply the new keys into the executable and then you also to want make sure you update your TBLs as well by clicking `Update Data Encryption`.

### Preview

![](/media/main_window.png)

You can also view detailed report of the target executable:

![](/media/general_window.png)

If some of the offsets were marked in red, it's because the middle key were inlined by the compiler, but don't worry, key1 and key3 will still be patched:

![](/media/general_window_inlined.png)

Also note that it detects the encryption algorithm used for the TBLs:

![](/media/general_window_encryption.png)

After patching, It is recommended to save the report seen in the previous pictures, or you could also save the log file generated that has more technical details:

![](/media/generated_logs.png)

## Contributing

Pull-Requests are greatly appreciated should you like to contribute to the project. 

Same goes for opening issues; if you have any suggestions, feedback or you found any bugs, please do not hesitate to open an [issue](https://github.com/ko4life-net/KO-TBLCryptoEditor/issues) or reach out at [ko4life.net](https://www.ko4life.net/).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
