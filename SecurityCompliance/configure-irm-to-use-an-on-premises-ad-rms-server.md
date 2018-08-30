---
title: オンプレミスの AD RMS サーバーを使用するように IRM を構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
description: このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。
ms.openlocfilehash: 82eed73797cfb4ade04bfeed9118d8466c5c5480
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002791"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>オンプレミスの AD RMS サーバーを使用するように IRM を構成する
  
設置型展開で使用するためは、Exchange Online の情報権利管理 (IRM) は、Active Directory Rights Management サービス (AD RMS) と後で Windows Server 2008 では、情報保護の技術を使用します。IRM による保護は、電子メール メッセージに AD RMS 権利ポリシー テンプレートを適用することにより、電子メールに適用されます。権限は、オンラインとオフラインと内部と外部の組織のファイアウォールの保護が行われるように、メッセージ自体に添付されます。
  
このトピックでは、AD RMS サーバーを使用して IRM を構成する方法を示します。Azure Active Directory と Azure のアクセス権の管理と Office 365 のメッセージの暗号化の新しい機能の使用方法の詳細については、 [Office 365 のメッセージの暗号化の FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)を参照してください。
  
Exchange Online の IRM については、「[Exchange Online での Information Rights Management](information-rights-management-in-exchange-online.md)」を参照してください。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- このタスクの予想所要時間:30 分
    
- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。 「[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「Information Rights Management」。 
    
- AD RMS サーバーは、Windows Server 2008 以降を実行している必要があります。AD RMS を展開する方法については、「[AD RMS クラスターのインストール](https://go.microsoft.com/fwlink/?LinkId=210873)」を参照してください。
    
- Windows PowerShell のインストール方法と構成方法、およびサービスへの接続方法については、「[リモート PowerShell による Exchange への接続](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)」を参照してください。
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="how-do-you-do-this"></a>実行方法
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>手順 1:AD RMS コンソールを使用して、AD RMS サーバーから信頼された発行ドメイン (TPD) をエクスポートします。

まず、信頼された発行ドメイン (TPD) を社内 AD RMS サーバーから XML ファイルにエクスポートします。TPD には RMS 機能を使用するために必要な以下の設定が含まれています。 
  
- 証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)
    
- ライセンスと発行に使用される URL
    
- TPD に固有の SLC を使用して作成された AD RMS 権利ポリシー テンプレート
    
TPD をインポートすると、Exchange Online に保存され、保護されます。
  
1. Active Directory Rights Management サービスのコンソールを開いて、AD RMS クラスターを展開します。
    
2. コンソール ツリーで、 **[信頼ポリシー]** を展開してから、 **[信頼された発行ドメイン]** をクリックします。
    
3. 結果ウィンドウで、エクスポートするドメインの証明書を選択します。
    
4. **[操作]** ウィンドウで、 **[信頼された発行ドメインのエクスポート]** をクリックします。
    
5. **[発行ドメイン ファイル]** の **[名前を付けて保存]** をクリックして、ローカル コンピューター上の特定の場所にファイルを保存します。ファイル名を入力して、  `.xml` ファイル名拡張子を指定してから、 **[保存]** をクリックします。
    
6. **[パスワード]** ボックスと **[パスワードの確認入力]** ボックスに、信頼された発行ドメイン ファイルの暗号化に使用する強力なパスワードを入力します。このパスワードは、クラウドベースの電子メール組織に TPD をインポートするときに指定する必要があります。 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>手順 2: Exchange 管理シェル を使用して TPD を Exchange Online にインポートする

TPD を XML ファイルにエクスポートした後は、TPD を Exchange Online にインポートする必要があります。TPD をインポートすると、組織の AD RM テンプレートもインポートされます。最初の TPD をインポートすると、それがクラウドベース組織の既定の TPD になります。別の TPD をインポートする場合は、 **Default** スイッチを使用してこの TPD を既定の TPD にし、ユーザーが使用できるようにすることができます。 
  
TPD をインポートするには、Windows PowerShell で次のコマンドを実行します。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

_ExtranetLicensingUrl_ パラメーターと  _IntranetLicensingUrl_ パラメーターの値は、Active Directory Rights Management サービスのコンソールで取得できます。コンソール ツリーで AD RMS クラスターを選択します。ライセンスの URL が結果ウィンドウに表示されます。コンテンツを復号化する必要がある場合と使用する TPD を Exchange Online で決定する必要がある場合は、これらの URL が電子メール クライアントによって使用されます。 
  
このコマンドを実行すると、パスワードの入力を求めるプロンプトが表示されます。TPD を AD RMS サーバーからエクスポートしたときに指定したパスワードを入力します。
  
たとえば、次のコマンドは、AD RMS サーバーからエクスポートして管理者アカウントのデスクトップに保存された XML ファイルを使用して、Exported TPD という名前の TPD をインポートします。Name パラメーターは TPD の名前を指定するために使用されます。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

構文およびパラメーターの詳細については、「[Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)」を参照してください。
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

TPD が正常にインポートされたことを確認するには、 **Get-RMSTrustedPublishingDomain** コマンドレットを実行して Exchange Online 組織の TPD を取得します。詳細については、「 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx)」内の例を参照してください。
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>手順 3: Exchange 管理シェル を使用して AD RMS 権利ポリシー テンプレートを配布する

TPD をインポートしたら、AD RMS 権利ポリシー テンプレートが配布されていることを確認する必要があります。配布済みテンプレートは Outlook Web App ユーザーに対して表示され、電子メール メッセージに適用できるようになります。
  
既定の TPD に含まれているすべてのテンプレートの一覧を取得するには、次のコマンドを実行します。
  
```
Get-RMSTemplate -Type All | fl
```

_Type_ パラメーターの値が  `Archived` の場合は、テンプレートがユーザーに対して表示されません。既定の TPD に含まれている配布済みテンプレートだけを Outlook Web App で使用できます。
  
テンプレートを配布するには、次のコマンドを実行します。
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

たとえば、次のコマンドは、Company Confidential テンプレートをインポートします。
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

構文とパラメーターの詳細については、「[Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)」と「[Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)」を参照してください。
  
 **転送不可テンプレート**
  
既定の TPD を社内組織から Exchange Online にインポートすると、 **Do Not Forward** という名前の AD RMS 権利ポリシー テンプレートが 1 つインポートされます。既定で、このテンプレートは、既定の TPD をインポートしたときに配布されます。 **Set-RMSTemplate** コマンドレットを使用して **Do Not Forward** テンプレートを変更することはできません。 
  
**Do Not Forward** テンプレートがメッセージに適用されている場合は、メッセージにアドレスが指定された受信者のみがメッセージを読むことができます。受信者が次の操作を行うことはできません。 
  
- メッセージを別のユーザーに転送する。
    
- メッセージの内容をコピーする。
    
- メッセージを印刷する。
    
> [!IMPORTANT]
> **Do Not Forward** テンプレートは、サードパーティのスクリーン キャプチャ プログラムやカメラを使用してメッセージ内の情報がコピーされたり、ユーザーによって情報が書き写されるのを防げるわけではありません。 
  
IRM 保護要件に合わせて、社内組織内の AD RMS サーバー上に追加の AD RMS 権利ポリシー テンプレートを作成できます。追加の AD RMS 権利ポリシー テンプレートを作成する場合は、TPD を社内 AD RMS サーバーから再びエクスポートして、クラウドベースの電子メール組織の TPD を更新する必要があります。 
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

AD RMS 権利ポリシー テンプレートが正常に配布されたことを確認するには、 **Get-RMSTemplate** コマンドレットを実行してテンプレートのプロパティをチェックします。詳細については、「 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)」内の例を参照してください。
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>手順 4: Exchange 管理シェル を使用して IRM を有効にする

TPD をインポートして AD RMS 権利ポリシー テンプレートを配布したら、次のコマンドを実行して、クラウドベースの電子メール組織に対して IRM を有効にします。
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

構文およびパラメーターの詳細については、「[Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)」を参照してください。
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

IRM が正常に有効になったことを確認するには、[Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) コマンドレットを実行して、Exchange Online 組織内の IRM 構成をチェックします。 
  
## <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法
<a name="sectionSection2"> </a>

TPD が正常にインポートされ、IRM が有効になったことを確認するには、次の手順を実行します。
  
- IRM の機能をテストするには、 **Test-IRMConfiguration** コマンドレットを使用します。詳細については、「 [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)」の「例 1」を参照してください。
    
- Outlook Web App で新しいメッセージを作成し、拡張メニュー (****[その他のオプション] アイコン![) で ](media/ITPro-EAC-MoreOptionsIcon.gif) オプションを選択して、そのメッセージを IRM で保護します。
    

