# S105\_1 請求先登録

### 請求先情報部

{% tabs %}
{% tab title="項目制御" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left">No</th>
      <th style="text-align:left">名称</th>
      <th style="text-align:left">
        <p>更新</p>
        <p>表示</p>
      </th>
      <th style="text-align:left">部品種類</th>
      <th style="text-align:left">必須</th>
      <th style="text-align:left">文字数</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">顧客名</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">請求先名</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">100</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">ふりがな</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">200</td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">請求先担当者</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">50</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">郵便番号</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">8</td>
    </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left">都道府県</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">50</td>
    </tr>
    <tr>
      <td style="text-align:left">7</td>
      <td style="text-align:left">住所</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">300</td>
    </tr>
    <tr>
      <td style="text-align:left">8</td>
      <td style="text-align:left">保存</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">button</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">9</td>
      <td style="text-align:left">戻る</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">button</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="詳細仕様" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left">No</th>
      <th style="text-align:left">名称</th>
      <th style="text-align:left">表示条件/仕様</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">顧客名</td>
      <td style="text-align:left">GETにセットされているcustomerIdから[customerId - name]を表示</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">ふりがな</td>
      <td style="text-align:left">ひらがなのみ保存可能</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">郵便番号</td>
      <td style="text-align:left">数値のみ保存可能</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">郵便番号</td>
      <td style="text-align:left">xxx-xxxx という形のみ許容</td>
    </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left">都道府県</td>
      <td style="text-align:left">
        <p>入力した郵便番号から自動提案</p>
        <p>変更不可</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">7</td>
      <td style="text-align:left">住所</td>
      <td style="text-align:left">
        <p>入力した郵便番号から自動提案</p>
        <p>変更可</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">8</td>
      <td style="text-align:left">保存</td>
      <td style="text-align:left">
        <p>保存APIを実行</p>
        <p>・失敗した場合、当画面に止まり、APIから返却された</p>
        <p>エラーメッセージを表示する</p>
        <p>・成功した場合、登録完了しましたメッセージ表示</p>
        <p>・登録完了しましたメッセージ表示後、S105_2 請求先編集画面へ遷移する</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">9</td>
      <td style="text-align:left">戻る</td>
      <td style="text-align:left">前の画面に戻る</td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="保存API" %}
#### 使用API

billingSave

| No | 名称 | パラメータ名 |
| :--- | :--- | :--- |
| 1 | 顧客名 | customerId |
| 2 | 請求先名 | name |
| 3 | ふりがな | kana |
| 4 | 請求先担当者 | staffName |
| 5 | 郵便番号 | zip |
| 6 | 都道府県 | address1 |
| 7 | 住所 | address2 |
{% endtab %}

{% tab title="その他API" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left">No</th>
      <th style="text-align:left">名称</th>
      <th style="text-align:left">タイミング</th>
      <th style="text-align:left">API</th>
      <th style="text-align:left">内容</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">郵便番号</td>
      <td style="text-align:left">更新時</td>
      <td style="text-align:left">addressSearch</td>
      <td style="text-align:left">
        <p>入力した郵便番号を[zipCode]にセットする</p>
        <p>返却された情報を元に[都道府県][住所]項目を更新する</p>
        <p>検索結果が0件の場合、バリデーションNG</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}
{% endtabs %}

