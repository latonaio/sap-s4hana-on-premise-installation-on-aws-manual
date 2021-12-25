# AWS Launch Wizard でのインスタンスの作成

インスタンスを [AWS Launch Wizard](https://us-west-2.console.aws.amazon.com/launchwizard/home) を使用して構築します。

- [AWS Launch Wizard](https://us-west-2.console.aws.amazon.com/launchwizard/home) から、「Choose Application」→「SAP」を選択します。

- 指示に従って設定・作成を行います。必要な設定は次のとおりです。

	- Define infrastructure ページ ([スクリーンショット](./launchwizard.dir/s1.png))
    	- Deployment name
    	- S3 file path
    	- Configuration name
    	- Key pair name
    	- Virtual Private Cloud (VPC)
    	- Availability Zone 1, Private subnet 1
    	- Availability Zone 2, Private subnet 1
    	- Verify connectivity
    	- IP Address/CIDR: Value: アクセスを許可したい IP アドレスレンジを任意に記述します。
    	- Time zone

	- Configure deployment model ページ ([スクリーンショット](./launchwizard.dir/s3.png))
    	- Distributed instance deployment
    	- Operating system and version (2 箇所あります)

	- Configure SAP application software installation ([スクリーンショット](./launchwizard.dir/s4.png))
    	- Application
    	- Version
    	- アップロードした SAP コンポーネントの保存先
        	- SAPCAR location
        	- Software Provisioning (SWPM) location
        	- Kernel software location
        	- Installation Export location
        	- HANA database software location
        	- SAP HANA client software location
    	- Master password
    	- S3 file path (SAP HANA バックアップの保存先)
		- Required policy attached to role
