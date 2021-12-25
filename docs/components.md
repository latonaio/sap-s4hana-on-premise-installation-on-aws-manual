# 必要なコンポーネントの取得と AWS へのアップロード

このページは、SAP のインスタンスを立ち上げるにあたって必要なコンポーネントの取得手順とAWSへのアップロード手順を記載しています。

## （ローカルへの）ダウンロード

[AWS 公式ページ](https://docs.aws.amazon.com/launchwizard/latest/userguide/launch-wizard-sap-software-install-details.html) の案内に従って、[SAP](https://launchpad.support.sap.com/#/softwarecenter) からコンポーネントのダウンロードを行います。

- SWPM

    - 「SUPPORT PACKAGES & PATCHES」タブの「SOFTWARE PROVISIONING MANAGER」→「SOFTWARE PROVISIONING MANAGER 2.0」内の最新版を取得します。

- SAPCAR

    - ファイル名を検索して取得します。(または「SUPPORT PACKAGES & PATCHES」タブの「SAPCAR」→「SAPCAR 7.22」→「SAPCAR_1010-70006178.EXE」を取得します。)

- Exports

    - 「Installations & Upgrades」タブの「SAP S/4 HANA」→「SAP S/4 HANA 2020」→「INSTALLATION (AUTOM. DOWNLOAD)」内のファイル名に EXPORT が含まれているファイルを取得します。また、英語と日本語の言語ファイルもあわせて取得します。

- Kernel components

    - AWS 公式ページに記載のあるファイルをファイル名で検索して取得します。または、次のとおり取得します。
        - SAPEXE_15-70005283.SAR, SAPEXEDB_15-70005282.SAR: 「SUPPORT PACKAGES & PATCHES」タブの「SAP KERNEL 64-BIT UNICODE」→「SAP KERNEL 7.81 64-BIT UNICODE」内にあります。また、SAPEXEDB は同ページ内のセレクトボックスから「SAP HANA DATABASE」を選択すると表示されます。
        - igsexe_0-70005417.sar: 「SUPPORT PACKAGES & PATCHES」タブの「SAP IGS」→「SAP IGS 7.81」内にあります。
        - igshelper_17-10010245.sar: 「SUPPORT PACKAGES & PATCHES」タブの「SAP IGS HELPER APPLICATIONS」→「SAP IGS HELPER」内にあります。
        - SAPHOSTAGENT49_49-20009394.SAR: 「SUPPORT PACKAGES & PATCHES」タブの「SAP HOST AGENT」→「SAP HOST AGENT 7.21」内にあります。

- SAP HANA Client

    - AWS 公式ページに記載のあるファイルを取得します。(「SUPPORT PACKAGES & PATCHES」→「SAP HANA PLATFORM EDITION」→「SAP HANA PLATFORM EDITION 2.0」→「SAP HANA CLIENT 2.0」内にあります。)

- SAP HANA Database software
    - AWS 公式ページに記載のある SP (SPS) の最新版を取得します。SPS (Support Package Stack) の番号が異なると動作しないので注意してください。<br />
      ファイルは「Installations & Upgrades」タブの「SAP IN-MEMORY (SAP HANA )」→「HANA PLATFORM EDITION」→「SAP HANA PLATFORM EDITION」→「SAP HANA PLATFORM EDITION 2.0」→「INSTALLATION」内にあります。

## AWSへのアップロード

https://s3.console.aws.amazon.com/s3/home にアクセスし、バケットを任意の名前で作成します。

AWS CLI から次の手順で取得したファイルをアップロードしてください。

```sh
aws s3 cp [アップロード元フォルダー] s3://[バケット名] --recursive
```

なお、フォルダー名にスペースなどの特殊記号を含まないよう注意してください。
