---
title: Microsoft Outlook 用迷惑メール報告アドインのインストール
ms.author: MSFTTracyP
author: tracyp
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: この articleSupported LanguagesInstall the 迷惑メール報告アドインをアンインストールします。迷惑メール報告アドインをアンインストールする inFor 詳細情報
ms.openlocfilehash: c9211cd71fd82af2b9fc0533435ff27a82cd47be
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152559"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook 用迷惑メール報告アドインのインストール
  
このトピックでは、Outlook 用 Microsoft 迷惑メール報告アドインを組織内のクライアント コンピューターにインストール (およびアンインストール) する方法を説明します。アドイン (2016 年 1 月) の現在のバージョンには、Outlook 2016、Outlook 2013、Outlook 2010、Outlook 2007 のサポートが含まれています。 
  
この (サポートされているすべての言語の) アドインで、Outlook のリボンから直接、迷惑メールを報告できます。英語版アドインには、リボンから直接マイクロソフトにメールの問題を報告するための追加のオプションが含まれています。
  
-  受信したフィッシング詐欺メールを報告してください。 
    
- 迷惑メールとして誤って識別されたメールを報告してください。
    
## <a name="supported-languages"></a>サポートされている言語
<a name="sectionSection0"> </a>

迷惑メール報告アドインは次の言語をサポートしています。 
  
- 簡体字中国語
    
- 繁体字中国語
    
- オランダ語
    
- 英語
    
- フランス語
    
- ドイツ語
    
- イタリア語
    
- 日本語
    
- 韓国語
    
- ポルトガル語
    
- ポルトガル語 (ブラジル)
    
- スペイン語
    
## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをインストールする
<a name="sectionSection1"> </a>

次の手順で、迷惑メール報告アドインをインストールします。
  
- 他の .msi ファイルと同様に Windows インストーラー パッケージを実行する。アドインをインストールする際、GUI インターフェイスが開き、インストール画面で手順が示されます。詳細については、「[セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard)」をご覧ください。
    
- インストール ユーザー インターフェイスを表示しないサイレント インストールを実行する。インストール スクリプトを実行するコマンドライン オプションを指定します。アドインをインストールする際、GUI インターフェイスでは提供されない追加の構成オプションが使用できます。詳細については、「[サイレント モードで迷惑メール報告アドインをインストールする](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode)」をご覧ください。
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

Microsoft Outlook 用 Microsoft 迷惑メール報告アドインのインストール要件は次のとおりです。
  
- 次のオペレーティング システムのいずれか:Windows 10、Windows 8.1、Windows 8、Windows 7 Service Pack 1、Windows 10 Server、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2
    
- Outlook 2016、Outlook 2013、Outlook 2010、または Outlook 2007 (Service Pack 2 以降)
    
- Microsoft Office プライマリ相互運用機能アセンブリ: 
    
  - Microsoft Office 2010 以上に対応したプライマリ相互運用機能アセンブリをダウンロードするには、[Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=166026) にアクセスしてください。
    
  - Microsoft Office 2007 に対応したプライマリ相互運用機能アセンブリをダウンロードするには、[Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=72637) にアクセスしてください。
    
- Microsoft .NET Framework [2.0 ](https://go.microsoft.com/fwlink/?LinkID=208706)。
    
> [!NOTE]
> このアドインをインストールするコンピューターの管理者特権が必要です。 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする
<a name="BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard"> </a>

1. お使いのコンピューターで Outlook を終了します。
    
2. Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook を入手するには、Microsoft Download Center ([https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248)) にアクセスし, .msi ファイルをダウンロードしてください。 
    
3. .msi ファイルをダブルクリックします。 
    
4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。 
    
5. 使用許諾契約書を確認し、インストール条件に同意する場合は、 **[使用許諾契約書の条件に同意する]** をクリックします (インストールを続行するには必須)。続行するには、 **[次へ]** をクリックします。 
    
6. ウィザードが完了したら、 **[完了]** をクリックします。 
    
7. Outlook を起動します。
    
8. Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。 
    
9. Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>サイレント モードで迷惑メール報告アドインをインストールする
<a name="BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode"> </a>

1. お使いのコンピューターで Outlook を終了します。
    
2. コマンド プロンプトを開きます。
    
3. オプション パラメーターを使用せずに、アドインを直接インストールしたい場合は、以下を指定します。
    
  - x86 Outlook を実行しているコンピューター: `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - X 64 Outlookを実行しているコンピューター: `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    オプションの MaxMessageSelection および BccEmailAddress パラメーターを指定することもできます。
    
  - MaxMessageSelection 管理者は、ユーザーが 1 回のクリックで送信する対象として選択できる最大メッセージ数を定義できます。範囲は 1 ～ 50 件で、既定値は 10 件です。
    
    Example: If you want to set the maximum number of messages that can be selected by users for submission in a single click to 16, use the following option as part of the installation command:  `MaxMessageSelection=16`
    
  - BccEmailAddress 管理者は、Bcc 電子メール アドレスを設定することで、ユーザーによるすべての送信のコピーを受信するようにメールボックスを設定できます。メールボックスを設定すると、送信されたすべての電子メールのコピーが BccEmailAddress に送信されます。この設定を行わない場合、既定の設定に Bcc 電子メール アドレスはありません。
    
    Example: If you want to use junkReports@contoso.com as the Bcc email address for all submissions, use the following command:  `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > セミコロンで区切って入力することで、複数の Bcc 電子メール アドレスを設定できます。例:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    上記の例に基づいてこれら両方のオプション パラメーターを追加するには、x86 Outlook を実行しているコンピューターで以下を指定します。 
    
  ```
  msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
  ```

4. インストールが完了したら、Outlook を起動します。
    
5. Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。 
    
6. Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする
<a name="sectionSection2"> </a>

迷惑メール報告アドインは、次のオプションのいずれかでアンインストールできます。
  
- Windows コントロール パネルを使用してアドインを削除する。詳細については、「[コントロール パネルから迷惑メール報告アドインをアンインストールする](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel)」をご覧ください。
    
- Windows インストーラー パッケージを実行し、アンインストール オプションを選択する。詳細については、「[Windows インストーラー パッケージを実行して迷惑メール報告アドインをアンインストールする](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage)」をご覧ください。
    
- アンインストール オプションを使用して、サイレント インストールを実行する。詳細については、「[サイレント モードで迷惑メール報告アドインをアンインストールする](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#MK_UninstalltheJunkEmailReportingAdd-ininSilentMode)」をご覧ください。
    
> [!NOTE]
> このアドインをアンインストールするコンピューターの管理者特権が必要です。 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>コントロール パネルから迷惑メール報告アドインをアンインストールする
<a name="BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel"> </a>

1. お使いのコンピューターで Outlook を終了します。
    
2. コンピューターの [スタート] メニューから **[コントロール パネル]** を選択します。
    
3. **[プログラムと機能]** を選択します。
    
4. **[Microsoft Junk E-mail Reporting Add-In for Microsoft Office Outlook]** を選択します。
    
5. **[アンインストール]** を選択します。
    
6. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Windows インストーラー パッケージを実行して迷惑メール報告アドインをアンインストールする
<a name="BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage"> </a>

1. お使いのコンピューターで Outlook を終了します。
    
    > [!NOTE]
    > アンインストール プロセス中に Outlook が稼働している場合は、アドインを完全にアンインストールするために、再起動する必要があります。 
  
2. 以前にアドインをインストールするために実行した .msi ファイルを再度実行します 
    
    (Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook を入手するには、Microsoft Download Center ([https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248)) にアクセスして, .msi ファイルをダウンロードし、ダブルクリックしてください)。 
    
3. 表示されるメッセージに従って、アドインをアンインストールします。
    
4. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>サイレント モードで迷惑メール報告アドインをアンインストールする
<a name="MK_UninstalltheJunkEmailReportingAdd-ininSilentMode"> </a>

1. お使いのコンピューターで Outlook を終了します。
    
    > [!NOTE]
    > アンインストール プロセス中に Outlook が稼働している場合は、アドインを完全にアンインストールするために、再起動する必要があります。 
  
2. コマンド プロンプトを開きます。
    
3. 次のコマンド ライン パラメーターを指定します。
    
    x86 Outlook を実行しているコンピューター: `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    X 64 Outlookを実行しているコンピューター: `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。
    
## <a name="for-more-information"></a>関連情報
<a name="sectionSection3"> </a>

[迷惑メール メッセージを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)
  
[トラブルシューティングとサポート情報](troubleshooting-and-support-information.md)
  

