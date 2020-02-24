# Docx File Auto Translation

## Basics

This *Mathematica* program use Google Translate to translate text.

It takes in a .docx file and output a .docx file, where translated texts are append after the original text.

A sample .docx file: `test.docx` is in the folder and the corresponding output is `test_out.docx`, One can see that all text are translated, including normal text, text in graphics and grids, texts in footnotes and endnotes. but all formats are kept intact, this is really convenient, isn't it!



For other languages, write:

```mathematica
TranslateAll[fromfile,tofile,GoogleTranslate,"TranslateFrom"->"**","TranslateTo"->"**"]
```

The default setting is from **English** to **Chinese**.



## Screenshot as follows:

### **Original `test.docx`**

![Original_1](https://i.loli.net/2018/04/03/5ac25e3fa7487.png)

![Original_2](https://i.loli.net/2018/04/03/5ac25e3fbea25.png)

### **Translated `test_out.docx`**

![Translated_1](https://i.loli.net/2018/04/03/5ac25e3fc0836.png)

![Translated_2](https://i.loli.net/2018/04/03/5ac25e3fc2689.png)



## Disclaimer

**This program requires *Mathematica* Version 11.0+ and `WebTools` package re-written by me......**

**If you failed to use this piece of code, it's probably because of an improperly installed `WebTools` Package**

**Using Google Translate extensively without paying is actually not that good... So please do not use it tooooo heavily...**

**This is only for study use! No commercial use allowed!!!**



## For Further Devs

1. `GoogleTranslate` is a convenient function to use~

2. *Translate* is used in the broad sense here, essentially all forms of operation to a sentence could be called as *Translate*. In fact, all translate work is done by function `GoogleTranslate` as a parameter of function `TranslateAll`, so if one substitute this with other functions such like `Function[{string},somecode]&`, it would work as well. A simple "repeat the content three times" program could be:

   ```mathematica
   TranslateAll[fromfile,tofile,StringJoin[ConstantArray[#,2]]&]
   ```

3. Further development include saving progress once in a while instead of dumping it altogether when the whole translation process ends. Now any interruption would cause the program to fail... Though I've used it to translate documents hundreds of pages long without a failure... This could be greatly improved, and it's not hard. But I'm to lazy to do it... (But note that this process is not as easy as one might think, a tiny validity check of some sort must be added before exporting to ensure that exported document is valid, not falsely created.)
