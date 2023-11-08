# 命名規則
1. 半角英数字、半角アンダースコアのみを使用してください。
2. 最初の文字は、半角英数字である必要があります。
3. 全てのコード、ファイル名にスネークケースを採用します。
4. 分かりやすい名前を使用してください。
5. 予約語の仕様を避けてください。
6. 一貫性を持たせてください。
7. UnrealEngineのファイルの名前は先頭にファイルの種類を大文字で表してください。
8. 定数である場合は、すべて大文字で記述してください。
9. 名前空間はパスカルケースを採用してください。
10. コメントは全てに付けてください。
11. 作成者を一番上の位置に明記してください。

### Example
ファイル名: `example_file_name.txt`<br>
UEファイル名: `BP_example_function`
```cpp
//
// Created by Example
// yyyy/mm/dd
//

// Include space
#include <iostream>

// What is this namespace
namespace ThisIsNamespace{}

// What is this class
class this_is_class{
    // What is this variable
    int this_is_variable;
    // What is this variable
    const int THIS_IS_CONST_VARIABLE;

    // What is thi method
    void this_is_method;
}

```
