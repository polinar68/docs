---
title: プロジェクトへの変更のコミットやレビュー
intro: '{{ site.data.variables.product.prodname_desktop }}では、ファイルを編集すると、全ての変更が追跡されます。 有意義なコミットを作成するために、変更のまとめ方を決めることができます。'
versions:
  free-pro-team: '*'
---

### コミットについて

ファイルの保存と同様に、コミットは、ブランチにある１つ以上のファイルの変更です。 Gitは、各コミットに次の情報を追跡するSHA、またはハッシュという固有のIDを割り当てます。

- 具体的な変更
- 変更時間
- 変更者

コミットするときは、変更を簡潔に説明するコミットメッセージを含める必要があります。 共同作業しているコミットに共著者を追加することもできます。

### 1. ブランチの選択と変更の実行

1. [新規ブランチを作成する](/desktop/guides/contributing-to-projects/managing-branches)か、ツールバーにある{% octicon "git-branch" aria-label="The branch icon" %}**Current Branch**をクリックし、既存ブランチをリストから選択します。 ![現在のブランチを切り替えるドロップダウンメニュー](/assets/images/help/desktop/click-branch-in-drop-down.png)
{{ site.data.reusables.desktop.make-changes }}

### 2. コミットに含める変更の選択方法

テキストエディタでファイルに変更を加えて保存していくと、変更は、{{ site.data.variables.product.prodname_desktop }}にも反映されます。

* 赤い{% octicon "diff-removed" aria-label="The diff removed icon color-red" %}アイコンは、削除されたファイルを表します。
* 黄色の{% octicon "diff-modified" aria-label="The diff modified icon color-yellow" %}アイコンは変更されたファイルを表します。
* 緑の{% octicon "diff-added" aria-label="The diff added icon color-green" %}アイコンは、追加されたファイルを表します。
* stash した変更にアクセスするには、[**Stashed Changes**] をクリックします。 ![[Stash changes] オプション](/assets/images/help/desktop/stashed-changes.png)
* {{ site.data.reusables.desktop.commit-all-desc }}
![チェックボックスを選択して、変更されたすべてのファイルをコミットします](/assets/images/help/desktop/commit-all.png)
* {{ site.data.reusables.desktop.commit-some-desc }}
![コミットするファイルの横のチェックボックスを選択します](/assets/images/help/desktop/commit-some.png)

#### 部分的なコミットの作成方法

1つのファイルに複数の変更があり、*一部*だけをコミットに含めたい場合は、部分的なコミットを作成できます。 追加変更やコミットできるように、他の変更はそのまま残ります。 これにより、改行の変更をコードや構文の変更から区別するなど、個別で有意義なコミットの作成が可能になります。

ファイルのdiffを確認するとき、コミットに含まれる行は青色で強調表示されます。 変更を除外するには、青色が消えるように変更された行をクリックします。

![ファイルで選択解除された行](/assets/images/help/desktop/partial-commit.png)

#### 変更の廃棄

1つのファイルや複数のファイルのコミットされていない全ての変更の廃棄、または最新コミット以降の全てのファイルの全ての変更の廃棄ができます。

{% mac %}

{{ site.data.reusables.desktop.select-discard-files }}
{{ site.data.reusables.desktop.click-discard-files }}
  ![コンテキストメニュー内の [Discard Changes] オプション](/assets/images/help/desktop/discard-changes-mac.png)
{{ site.data.reusables.desktop.confirm-discard-files }}
  ![確定ダイアログ内の [Discard Changes] ボタン](/assets/images/help/desktop/discard-changes-confirm-mac.png)

{% tip %}

**ヒント：**廃棄した変更は、Trash内の日付付きファイルに保存され、Trashが空になるまでは復元できます。

{% endtip %}

{% endmac %}

{% windows %}

{{ site.data.reusables.desktop.select-discard-files }}{{ site.data.reusables.desktop.click-discard-files }}
  ![コンテキストメニュー内の [Discard Changes] オプション](/assets/images/help/desktop/discard-changes-win.png)
{{ site.data.reusables.desktop.confirm-discard-files }}
  ![確定ダイアログ内の [Discard Changes] ボタン](/assets/images/help/desktop/discard-changes-confirm-win.png)

{% tip %}

**ヒント：**廃棄した変更は、Recycle Bin内のファイルに保存され、空になるまでは復元できます。

{% endtip %}

{% endwindows %}

### 3. コミットメッセージの入力と変更のプッシュ

コミットに含めたい変更を決めたら、コミットメッセージを入力して変更をプッシュします。 コミットで共同作業した場合、コミットに 1 人以上の作者を追加できます。

{% note %}

**Note**: {{ site.data.reusables.desktop.tags-push-with-commits }} For more information, see "[Managing tags](/desktop/contributing-to-projects/managing-tags)."

{% endnote %}

{{ site.data.reusables.desktop.commit-message }}
  ![Commit messageフィールド](/assets/images/help/desktop/commit-message.png)
2. オプションとして、コミットに別の作者を追加するには、共作者を追加するアイコンをクリックし、追加するユーザ名を入力します。 ![コミットメッセージに共作者を追加](/assets/images/help/desktop/add-co-author-commit.png)
{{ site.data.reusables.desktop.commit-button }}
  ![[Commit] ボタン](/assets/images/help/desktop/commit-button.png)
4. コミットしようとしているブランチが保護されている場合、Desktopは警告します。
    - 変更を移動するには、**switch branches（ブランチを切り替え）**をクリックしてください。
    - 保護されたブランチに変更をコミットするには、**Commit to _BRANCH_（ブランチにコミット）**をクリックしてください。

  保護されたブランチに関する詳しい情報については「[保護されたブランチについて](/github/administering-a-repository/about-protected-branches)」を参照してください。 ![保護されたブランチの警告](/assets/images/help/desktop/protected-branch-warning.png)
{{ site.data.reusables.desktop.push-origin }}