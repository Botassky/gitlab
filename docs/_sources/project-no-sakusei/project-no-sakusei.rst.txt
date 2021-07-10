.. _project-no-sakusei:

**************************************************
プロジェクトの作成
**************************************************
プロジェクトは Maintainer 以上の role を持つアカウントで作成できます。今回は Maintainer の role を持つアカウント jiro でプロジェクトを作成します。

----

#. GitLab サーバーにアカウント jiro でログイン

   .. image:: ./img/2020-07-12_05h44_37.png
      :scale: 65%

   |

#. :guilabel:`Create a project` をクリック

   .. image:: ./img/2020-07-12_05h44_48.png
      :scale: 65%

   |

#. 次の値を入力

   .. list-table::
      :widths: 1, 1, 2

      * - 項目
        - 入力値／選択値
        - 備考
      * - Project name
        - sample-project
        - プロジェクト名
      * - Project URL
        - staff
        - プルダウンリストからプロジェクトを紐付けるグループを選択
      * - Project slug
        - sample-project
        - "Project name" の値が自動的に設定される
      * - Project discription (optional)
        - sample project of staff group
        - プロジェクトの説明
      * - Visibility Level
        - Internal
        - :ref:`group-no-sakusei-Visibility-level` を参照
      * - Initialize repository with a README
        - チェックを入れる
        - プロジェクト内に README.md ファイルを作成し、リポジトリを初期化する

   .. image:: ./img/2020-07-12_05h45_51.png
      :scale: 65%

   |

#. :guilabel:`Create project` をクリック

   .. image:: ./img/2020-07-12_05h46_03.png
      :scale: 65%

   |


#. :guilabel:`settings`　→　:guilabel:`Repository` の順にクリック

   .. image:: ./img/2020-07-12_05h47_01.png
      :scale: 65%

   |

#. "Protected Branches" の :guilabel:`expand` をクリック

   .. image:: ./img/2020-07-12_05h49_49.png
      :scale: 65%

   |

#. 次の値を選択　→　:guilabel:`Unprotect` をクリック

   .. list-table::
      :widths: 1, 1, 2

      * - 項目
        - 選択値
        - 備考
      * - Allowed to merge
        - Developers + Maintainer
        - プルダウンリストから選択
      * - Allowed to push
        - Developers + Maintainer
        - プルダウンリストから選択

   .. image:: ./img/2020-07-12_05h51_45.png
      :scale: 65%

   |

#. :guilabel:`OK` をクリック

   .. image:: ./img/2020-07-12_05h52_02.png
      :scale: 65%

   |

#. :guilabel:`Project Overview` をクリック

   .. image:: ./img/2020-07-12_05h55_41.png
      :scale: 65%

   |

#. プロジェクトの作成終了

   .. image:: ./img/2020-07-12_05h56_02.png
      :scale: 65%

   |

.. _project-no-sakusei-sudeni-project-ga-arutoki:

すでにプロジェクトが存在するとき
==================================================
すでにプロジェクトが存在するとき、サインイン後にプロジェクトの一覧が表示されます。一覧の画面で :guilabel:`New project` をクリックして、新規プロジェクトを作成します。

#. GitLab サーバーにアカウント jiro でログイン

   .. image:: ./img/2020-07-12_06h23_52.png
      :scale: 65%

   |

#. :guilabel:`New project` をクリック

   .. image:: ./img/2020-07-12_06h24_00.png
      :scale: 65%

   |

後は、上述と同じ手順でプロジェクトを作成します。

|
