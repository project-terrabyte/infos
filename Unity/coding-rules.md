# コーディングルール
以下にコーディングルールに沿った例を示す。
```csharp
/**
 * ここにこのファイルの内容の要約を書く
 * Author: githubのアカウントURLを張り付ける
*/
using System.Collections; // using は全てコードの上に配置し、必要のないusingは使用しない
using System.Collections.Generic; // 自動生成で使わないusingは削除する
using UnityEditor;
using UnityEngine;

// 全ての作成したスクリプトは名前空間に属する
namespace ExampleNamespace { // 単語の先頭を大文字とするパスカルケースを採用する
    // 全てのスクリプトはpublicで作成する
    public class ExampleClass { // 単語の先頭を大文字とするパスカルケースを採用する
        // 変数は処理よりも前にまとめて記述する
        private int thisIsInt = 0; // 先頭を小文字、単語の頭文字を大文字とするキャメルケースを採用する
        private string thisIsString = "Example"; // 基本的に変数はプライベートで作成し、取得用の関数を用意する
        private Rigidbody rb;
        [SerializeField] private GameObject obj; // SerializeFieldは、スクリプトまたはオブジェクトを代入したいときにのみ使う

        // 処理の塊には、必ずリージョンを使用する
        #region Unity void method

        private void Start() {
            // 何をしているのかを必要であれば記述する
            rb = GetComponent<Rigidbody>();
        }
        // 処理間は1行開ける
        private void Update() {

            thisIsInt += 1;　// 処理はなるべくコンパクトにする　(ex) thisIsInt = thisIsInt + 1;とはしない

            if (thisIsInt % 10 == 0) { // if等のネストは最大で3を目標にする
                Debug.Log(GetThisIsString());
            }
        }

        #endregion

        #region Return Strings

        /// <summary>
        /// 基本的に変数はプライベートで作成し、取得用の関数を用意する
        /// 関数には必ずサマリーをつけ、他クラスから見ても何をしているのかわかるようにする
        /// </summary>
        public void GetThisIsString() { // 関数名は、端的に、識別しやすい名前を意識する
            return thisIsString;
        }

        #endregion
    }
}
// コードの終わりは一行追加する
```
