---
title: オンプレミスの AD RMS サーバーを使用するように IRM を構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。
ms.openlocfilehash: 1bfdde516b8c807e4805f8a827a26dda3d60d043
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699252"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>IRM を設定して、オンプレミスの AD RMS サーバーを使用する
  
オンプレミス展開でを使用する場合、Exchange Online の Information Rights Management (IRM) では、Windows Server 2008 以降の情報保護テクノロジである Active Directory Rights Management サービス (AD RMS) が使用されます。 IRM 保護を電子メールに適用するには、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用します。 権限はメッセージ自体に添付されているため、オンラインとオフラインの両方、および組織のファイアウォールの内外両方で保護が有効になります。
  
このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。 Azure Active Directory と Azure Rights Management を使用した Office 365 メッセージ暗号化の新機能の使用方法については、「 [office 365 のメッセージ暗号化](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)に関する FAQ」を参照してください。
  
Exchange Online の IRM については、「[Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)」を参照してください。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識
<a name="sectionSection0"> </a>

- このタスクの予想所要時間:30 分
    
- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「Information Rights Management」を参照してください。 
    
- AD RMS サーバーは、Windows Server 2008 以降を実行している必要があります。 AD RMS を展開する方法の詳細については、「 [AD Rms クラスターのインストール](https://go.microsoft.com/fwlink/?LinkId=210873)」を参照してください。
    
- Windows PowerShell のインストール方法と構成方法、およびサービスへの接続方法については、「[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)」を参照してください。
    
- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。
    
> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 > 一般法人向け Office 365 の管理者の場合は、サポートに問い合わせることができます。 
  
## <a name="how-do-you-do-this"></a>実行方法
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>手順 1:AD RMS コンソールを使用して、AD RMS サーバーから信頼された発行ドメイン (TPD) をエクスポートします。

まず、信頼された発行ドメイン (TPD) を社内 AD RMS サーバーから XML ファイルにエクスポートします。TPD には RMS 機能を使用するために必要な以下の設定が含まれています。 
  
- 証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)
    
- ライセンスと発行に使用される URL
    
- TPD に固有の SLC を使用して作成された AD RMS 権利ポリシー テンプレート
    
TPD をインポートすると、Exchange Online に格納され、保護されます。
  
1. Active Directory Rights Management サービスのコンソールを開いて、AD RMS クラスターを展開します。
    
2. コンソール ツリーで、**[信頼ポリシー]** を展開してから、**[信頼された発行ドメイン]** をクリックします。
    
3. 結果ウィンドウで、エクスポートするドメインの証明書を選択します。
    
4. **[操作]** ウィンドウで、**[信頼された発行ドメインのエクスポート]** をクリックします。
    
5. **[発行ドメイン ファイル]** の **[名前を付けて保存]** をクリックして、ローカル コンピューター上の特定の場所にファイルを保存します。 ファイル名を入力し、 `.xml`ファイル名拡張子を指定して、[**保存**] をクリックします。
    
6. **[パスワード]** ボックスと **[パスワードの確認入力]** ボックスに、信頼された発行ドメイン ファイルの暗号化に使用する強力なパスワードを入力します。このパスワードは、クラウドベースの電子メール組織に TPD をインポートするときに指定する必要があります。 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>手順 2: Exchange 管理シェルを使用して TPD を Exchange Online にインポートする

TPD を XML ファイルにエクスポートした後は、TPD を Exchange Online にインポートする必要があります。 TPD をインポートすると、組織の AD RM テンプレートもインポートされます。 最初の TPD をインポートすると、それがクラウドベース組織の既定の TPD になります。 別の TPD をインポートする場合は、**Default** スイッチを使用してこの TPD を既定の TPD にし、ユーザーが使用できるようにすることができます。 
  
TPD をインポートするには、Windows PowerShell で次のコマンドを実行します。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Active Directory Rights Management サービスコンソールで_ExtranetLicensingUrl_パラメーターと_IntranetLicensingUrl_パラメーターの値を取得できます。 コンソール ツリーで AD RMS クラスターを選択します。 ライセンスの URL が結果ウィンドウに表示されます。 コンテンツを復号化する必要がある場合と使用する TPD を Exchange Online で決定する必要がある場合は、これらの URL が電子メール クライアントによって使用されます。 
  
このコマンドを実行すると、パスワードの入力を求められます。 TPD を AD RMS サーバーからエクスポートしたときに指定したパスワードを入力します。
  
たとえば、次のコマンドは、AD RMS サーバーからエクスポートして管理者アカウントのデスクトップに保存された XML ファイルを使用して、Exported TPD という名前の TPD をインポートします。Name パラメーターは TPD の名前を指定するために使用されます。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

構文およびパラメーターの詳細については、「[Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)」を参照してください。
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

TPD が正常にインポートされたことを確認するには、 **import-rmstrustedpublishingdomain**コマンドレットを実行して、Exchange Online 組織内の tpds を取得します。 詳細については、「[Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx)」内の例を参照してください。
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>手順 3: Exchange 管理シェルを使用して AD RMS 権利ポリシーテンプレートを配布する

TPD をインポートしたら、AD RMS 権利ポリシー テンプレートが配布されていることを確認する必要があります。 分散テンプレートは、web 上の Outlook (旧称 Outlook Web App) ユーザーに表示され、その後、電子メールメッセージにテンプレートを適用できます。
  
既定の TPD に含まれているすべてのテンプレートの一覧を取得するには、次のコマンドを実行します。
  
```
Get-RMSTemplate -Type All | fl
```

_Type_パラメーターの値がの場合、 `Archived`テンプレートはユーザーに表示されません。 Web 上の Outlook では、既定の TPD で配布されたテンプレートのみを使用できます。
  
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
  
既定の TPD を社内組織から Exchange Online にインポートすると、**Do Not Forward** という名前の AD RMS 権利ポリシー テンプレートが 1 つインポートされます。 既定で、このテンプレートは、既定の TPD をインポートしたときに配布されます。 **Set-RMSTemplate** コマンドレットを使用して **Do Not Forward** テンプレートを変更することはできません。 
  
**Do Not Forward** テンプレートがメッセージに適用されている場合は、メッセージにアドレスが指定された受信者のみがメッセージを読むことができます。受信者が次の操作を行うことはできません。 
  
- メッセージを別のユーザーに転送する。
    
- メッセージの内容をコピーする。
    
- メッセージを印刷する。
    
> [!IMPORTANT]
> **Do Not Forward** テンプレートは、サードパーティのスクリーン キャプチャ プログラムやカメラを使用してメッセージ内の情報がコピーされたり、ユーザーによって情報が書き写されるのを防げるわけではありません。 
  
IRM 保護要件に合わせて、社内組織内の AD RMS サーバー上に追加の AD RMS 権利ポリシー テンプレートを作成できます。 追加の AD RMS 権利ポリシー テンプレートを作成する場合は、TPD を社内 AD RMS サーバーから再びエクスポートして、クラウドベースの電子メール組織の TPD を更新する必要があります。 
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

AD RMS 権利ポリシーテンプレートが正常に配布されたことを確認するには、 **get-rmstemplate**コマンドレットを実行してテンプレートのプロパティを確認します。 詳細については、「[Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)」内の例を参照してください。
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>手順 4: Exchange 管理シェルを使用して IRM を有効にする

TPD をインポートして AD RMS 権利ポリシー テンプレートを配布したら、次のコマンドを実行して、クラウドベースの電子メール組織に対して IRM を有効にします。
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

構文およびパラメーターの詳細については、「[Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)」を参照してください。
  
#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

IRM が正常に有効になったことを確認するには、 [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx)コマンドレットを実行して、Exchange Online 組織の irm 構成を確認します。 
  
## <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法
<a name="sectionSection2"> </a>

TPD が正常にインポートされ、IRM が有効になったことを確認するには、次の手順を実行します。
  
- IRM の機能をテストするには、**Test-IRMConfiguration** コマンドレットを使用します。 詳細については、「 [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)」の「例1」を参照してください。
    
- Web 上の Outlook で新しいメッセージを作成し、拡張メニュー ( ![[その他のオプション] アイコン](media/ITPro-EAC-MoreOptionsIcon.gif)) で [**アクセス許可の設定**] オプションを選択して、そのメッセージを IRM で保護します。
    

