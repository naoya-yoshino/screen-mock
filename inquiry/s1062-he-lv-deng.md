# S106\_2 問合履歴登録

### 問合履歴情報部

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
      <td style="text-align:left">顧客検索</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">button</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">顧客名</td>
      <td style="text-align:left">表示</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">問合担当者</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">50</td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">問合電話番号</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">100</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">問合メールアドレス</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">100</td>
    </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left">問合題名</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">200</td>
    </tr>
    <tr>
      <td style="text-align:left">7</td>
      <td style="text-align:left">問合内容</td>
      <td style="text-align:left">更新</td>
      <td style="text-align:left">textarea</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">1000</td>
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
      <td style="text-align:left">顧客検索</td>
      <td style="text-align:left">
        <p>GETパラメータにcustomerIdが存在する場合、 顧客APIを実行</p>
        <p>当ボタン非表示</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">顧客検索</td>
      <td style="text-align:left">
        <p>GETパラメータにcustomerIdが存在しない場合</p>
        <p>顧客検索ボタンを表示し、押下でS103_1 顧客一覧をPOPUP表示</p>
        <p>当画面に戻ってきた際、顧客APIを実行</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">顧客名</td>
      <td style="text-align:left">customerIdから[customerId - name]を表示</td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">問合電話番号</td>
      <td style="text-align:left">数値のみ保存可</td>
    </tr>
    <tr>
      <td style="text-align:left">8</td>
      <td style="text-align:left">保存</td>
      <td style="text-align:left">
        <p>保存APIを実行</p>
        <p>・失敗した場合、当画面に止まり、APIから返却された</p>
        <p>エラーメッセージを表示する</p>
        <p>・成功した場合、登録完了しましたメッセージ表示</p>
        <p>・登録完了しましたメッセージ表示後、S106_3 問合履歴編集画面へ遷移する</p>
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

**inquirySave**

| **No** | 名称 | パラメータ名 |
| :--- | :--- | :--- |
| 2 | 顧客名 | customerId |
| 3 | 問合担当者 | staff |
| 4 | 問合電話番号 | tel |
| 5 | 問合メールアドレス | email |
| 6 | 問合題名 | title |
| 7 | 問合内容 | contents |
{% endtab %}

{% tab title="顧客API" %}
#### 使用API

customerSearch

| No | 名称 | パラメータ名 |
| :--- | :--- | :--- |
| 2 | 顧客名 | customerId |

#### セット内容

| No | 名称 | パラメータ名 |
| :--- | :--- | :--- |
| 3 | 問合担当者 | staffName |
| 4 | 問合電話番号 | tel |
| 5 | 問合メールアドレス | email |
{% endtab %}
{% endtabs %}



