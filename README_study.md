# npmコマンド
jsベースで作成する場合は
`npx create-react-app プロジェクト名`
typescriptベースで作成するときは
`npx create-react-app プロジェクト名 --template typescript

# ローカルサーバー起動
`npm starrt`

# create-react-app時のファイル・ディレクトリ構成

  - ## そもそも推奨されるディレクトリ構成はない
    自由度が高く、公式でもそこまで考えなくてもいいと書いてあるらしい。
  
  - ## node_modules
    ライブラリの実態が入る場所。pythonで言うところの.venvフォルダ
  
  - ## publicフォルダ
    静的ファイル（HTML CSS、画像等の置き場所）
  
    - ### index.HTML
  アプリの土台となるhtmlファイル。reactはこの中の ```html <div id="root"></div>``` に描画される
  
  - ## src
    tsx(jsベースの場合はjsx)コードの置き場所
  
    - ### そもそもtsx/jsxとは
        javascript, typescript野中にhtmlを直接記述できる構文拡張
        最終的にbabelなどのツールでjavascript, typescriptに変換されて実行される
  
    - ### コンポーネント
        jsx/tsxの関数として定義される、画面のパーツ
        コンポーネントの例：
        ```tsx
        // 関数部分がコンポーネント
        function Practice() {  //関数名の先頭は大文字
            return <h1>Reactの練習</h1>;　//関数で定義するJSXを関数コンポーネント
        }
        
        
        
        関数部分をHTMLとしてレンダリング
        root.render(<Practice />);
        ```
        ![component](public/image.png)
    
    - ### app.tsx
        アプリのメイン画面を構成するコンポーネントを集めたファイル
        
    
    - ### index.tsx
        index.htmlに対して、app.tsxにあるコンポーネントの中からどれを流し込むかを決めるところ
        reactは基本的にflaskなどと違い、SPA(single page application)なので、index.htmlに対してどのコンポーネントを流し込むかで表示内容を決める。
        - index.tsxの中身
            ```tsx
            // 1. 必要な道具をインポート
            import React from 'react';
            import ReactDOM from 'react-dom/client';
            import App from './App';

            // 2. HTML側にある "root" という箱を特定する
            const root = ReactDOM.createRoot(
            document.getElementById('root') as HTMLElement
            );

            // 3. その箱の中に、Appコンポーネントを描画する
            root.render(
            <React.StrictMode>
                <App />
            </React.StrictMode>
            );
            ```
    - ### react-app-env.d.tsx
        typescriptの型定義に関するファイル 基本ノータッチでOK
    - ### package.json
        プロジェクト内でつs買っているライブラリ屋起動コマンドなどの定義
    - ### tsconfig.json
        typescriptの設定ファイル コンパイルのルール等が書かれているらしい

# typescript
  - ## 変数宣言子
    | 演算子 | 役割 |
    | ---- | ---- |
    | var | 関数外からはアクセスできない変数 |
    | let | {} =if文などのブロックスコープ外からアクセスできない変数 |
    | const | 定数 |
  - ## typescript : 静的型付け
    ```typescript
    # 変数演算子 変数名 : データ型 = データ
    let mojiretsu : String = "ricky"
    ```
  - ## typescriptのデータ型
    [typescriptのデータ型](https://qiita.com/Im0_3/items/2ebbee06b8ca293e26ba)
    - ### str:文字列
      - #### 文字列の結合
      - #### 文字列中のデータの埋め込み
      - #### 文字列の代表的なメソッド
    - ### number: 数値
      - #### 四則演算
      - #### number型の代表的なメソッド
    - ### bool : 真偽値
      - #### boolの代表的なメソッド
    - ### bigint : でかい数値
    - ### symbol: 一意で不変のデータ
    - ### null / undefined : 空のデータ
      - #### null / undefinedのユースケース
      - 


