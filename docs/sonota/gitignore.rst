.. _gitignore:

**************************************************
ステージングエリアから除外するファイルの指定
**************************************************
ビルドなどで作成できるファイルは版（バージョン）管理をする必要はありません。これらのファイルをステージングエリアに登録しなければ良いのですが、都度登録しないよう操作したり、間違って登録したものを除外するのは手間がかかります。このように Git の管理から除外したいファイルの指定に :file:`.gitignore` ファイルを使用します。 :file:`.gitignore` ファイルに除外したいファイルやフォルダーを記録すると、それらはステージングエリアへの登録から除外されます。

.. tip::

   - 「ステージングエリアに登録しない　＝　コミットしない　＝　リモートリポジトリに登録しない」になります。
   - :file:`.gitignore` ファイルに指定した内容はプロジェクト全体に影響します。
   - :file:`.gitignore` ファイルに指定する前に 1 回でもコミットしたファイルは :file:`.gitignore` ファイルに指定しても、その指定は無視されます。

| ● :ref:`gitignore-rule`
| ● :ref:`gitignore-sample`
| ● :ref:`gitignore-settei`
| ● :ref:`gitignore-gitlab`
| ● :ref:`gitignore-others`
| ● :ref:`gitignore-commit-file`

.. include:: ./gitignore-rule.txt
.. include:: ./gitignore-sample.txt
.. include:: ./gitignore-settei.txt
.. include:: ./gitignore-gitlab.txt
.. include:: ./gitignore-others.txt
.. include:: ./gitignore-commit-file.txt
