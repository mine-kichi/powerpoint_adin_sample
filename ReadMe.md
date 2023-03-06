### powerpointアドインサンプル
- 手順
    - 適当なマクロを作成し、.basファイルでエキスポート
    - 新しいパワーポイントファイルを開き、visual basic画面で.basファイルをインポート
    - customUIフォルダを作成してcustomUI.xmlを作成し、下記内容を記載。適宜変更
    ```
    <?xml version="1.0" encoding="utf-8"?>
    <customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui">
    <ribbon startFromScratch="false">
    <tabs>
    <tab id="MyTab1" label="タブ名">

    <group id="Group1" label="グループ名1">
    <button id="Button1-1" label="ボタン名1" imageMso="MacroPlay" size="normal" onAction="マクロ名1" />
    <button id="Button1-2" label="ボタン名2" imageMso="MacroPlay" size="normal" onAction="マクロ名2" />
    <button id="Button1-3" label="ボタン名3" imageMso="MacroPlay" size="normal" onAction="マクロ名3" />
    </group>
    </tab>
    </tabs>
    </ribbon>
    </customUI>
    ```
    - menu.pptmファイルを.zipにファイル名変更し、中をいじる
        - custumUIフォルダを入れる
        - _relsフォルダの中の.relsファイルを変更。下記追加
    ```
    <Relationship Id="myCustomUI" Type="http://schemas.microsoft.com/office/2006/relationships/ui/extensibility" Target="customUI/customUI.xml"/>
    ```
    - zipをpptmに戻せばリボンにタブが追加されているはず。
    - ppamファイルで別途保存すればアドインファイル作成完了。