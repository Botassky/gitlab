.. _kankyo-kochiku:

**************************************************
環境構築
**************************************************

.. _kankyo-kochiku-gitlab-ce-no-install:

GitLab CE のインストール
==================================================
「 `GitLab.JP: GitLab日本語情報サイト <https://www.gitlab.jp/>`_ 」の「 `セルフマネージドGitLabをインストール <https://www.gitlab.jp/install/?version=ce#centos-8>`_ 」を参考に以下の内容の Vagrantfile を作成し GitLab CE をインストールします。

.. code-block:: none

   $script = <<-'SCRIPT'
   sudo dnf install -y curl policycoreutils openssh-server openssh-clients
   sudo systemctl enable sshd
   sudo systemctl start sshd
   sudo firewall-cmd --permanent --add-service=http
   sudo firewall-cmd --permanent --add-service=https
   sudo systemctl reload firewalld
   sudo dnf install postfix
   sudo systemctl enable postfix
   sudo systemctl start postfix
   curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
   sudo EXTERNAL_URL="https://gitlab.local" dnf install -y gitlab-ce
   SCRIPT
   
   Vagrant.configure("2") do |config|
     if Vagrant.has_plugin?("vagrant-vbguest")
       config.vbguest.auto_update = false
     end
     config.vm.define :centos8 do |centos8|
       centos8.vm.box = "centos/8"
       centos8.vm.network "public_network", mac: "000d58000001", ip: "192.168.1.151"
       centos8.vm.hostname = "gitlab.local"
       centos8.vm.provider "virtualbox" do |vb|
         vb.name = "gitlab"
         vb.memory = "16384"
         vb.cpus = 4
       end
       centos8.vm.provision "shell", inline: $script
     end
   end

名前解決ができるよう "C:\\Windows\\System32\\drivers\\etc\\hosts" ファイルに次の内容を追記します。

.. code-block:: none

   192.168.1.151       gitlab.local

.. _kankyo-kochiku-gitlab-ce-no-dousa-kakunin:

GitLab CE のインストール結果の確認
==================================================
ブラウザーで　GitLab CE にアクセスし、正常にインストールできたか確認します。

#. :command:`https://gitlab.local/` にアクセスします。

   .. image:: ./img/2020-06-28_17h47_31.png

   |

#. この画面が表示されたらインストールは成功です。

   .. image:: ./img/2020-06-28_17h47_52.png

.. note::

   途中、セキュリティの警告が表示されたときは先へ進めてください。

.. _kankyo-kochiku-gitlab-ce-no-root-password-no-henko:

GitLab CE の root アカウントの password の変更
==================================================
GitLab CE の root アカウントのパスワードを変更します。

#. guilabel:`New password` と guilabel:`Confirm new password` に GitLab CE の root パスワードを入力　→　:guilabel:`Change your password` をクリック

   .. image:: ./img/2020-06-28_18h12_33.png

   |

#. 次の値を入力　→　:guilabel:`Sign in` をクリック

   .. list-table::
      :widths: 1, 2

      * - 項目
        - 入力値
      * - Username or email
        - root
      * - password
        - 1 つ前のステップで設定したパスワード
   
   .. image:: ./img/2020-06-28_18h13_26.png

   |

#. GitLab CE の root アカウントのパスワード変更が終了

   .. image:: ./img/2020-06-28_18h13_41.png
