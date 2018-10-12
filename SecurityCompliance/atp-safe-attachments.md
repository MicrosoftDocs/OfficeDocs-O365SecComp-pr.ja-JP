---
title: Office 365 の ATP の安全な添付ファイル
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全な添付ファイル機能は、電子メールの添付ファイルのクリックの検証を提供します。ファイルを悪意のあるユーザーから組織を保護するために使用の安全な添付ファイルで送信または受信電子メールです。
ms.openlocfilehash: a43f5aac30f074f6331d809c800005596a721204
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522268"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 の ATP の安全な添付ファイル

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 の ATP の安全な添付ファイルの概要

分析ツール ( [ATP の安全なリンク](atp-safe-links.md)) との安全な添付ファイルは、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の一部です。ATP の安全な添付ファイル機能では、電子メールの添付ファイルは、悪意のあるかどうかを確認し、組織を保護するために操作を行います。ATP の安全な添付ファイル機能は、Office 365 のグローバルまたはセキュリティ管理者によって設定されている[安全な添付ファイルの分析ツールのポリシー](set-up-atp-safe-attachments-policies.md)に従って、組織を保護します。 
  
最近では、ATP の保護が、SharePoint Online の OneDrive 内のファイルにビジネス、およびマイクロソフトのチームに拡張されました。詳細については、 [Office 365 高度な脅威保護](atp-for-spo-odb-and-teams.md)を参照してください。
       
### <a name="how-it-works"></a>しくみ

ATP の安全な添付ファイル機能は、組織内のユーザーの電子メールの添付ファイルをチェックします。ATP の安全な添付ファイル ポリシーが適用されて、他の対象となるポリシーが Office 365 に自分の電子メールを表示する、その電子メールの添付ファイルがチェックされ、ATP の安全な添付ファイル ポリシーに基づいて、適切な動作が実行します。ポリシーの定義方法によって、人は悪意のあるファイルを送信した順序を今まで知らなくても作業を続行できます。
  
作業で、ATP の安全な添付ファイルの 2 つの例を次に示します。
  
- **の例 1: 電子メールの添付ファイル**Lee がファイルの添付された電子メール メッセージを受信すると仮定します。Lee にわかりやすいかどうか添付ファイルが安全か、Lee のユーザーの資格情報を盗み出すように設計されたマルウェアが実際に含まれています。Lee の組織では、セキュリティ管理者は、数日前、ATP の安全な添付ファイル ポリシーを定義します。ATP の安全な添付ファイル機能を使用して電子メールの添付ファイルが開かれ、Lee では、それを受け取る前に、仮想環境でテストします。悪意のある添付ファイルが確認された場合に自動的に削除されます。添付ファイルが安全な場合に Lee をクリックしたときに期待どおりに開きます。 
    
- **例 2: SharePoint のオンラインでのファイル**Jean がファイルを受信して、SharePoint Online 内のライブラリにアップロードすることがあるとします。Jean は、ファイルが実際には悪意のあるであることも、チームの残りの部分とファイルへのリンクを共有します。幸いなことに、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを検出し、それをブロックします。数日後で、山口さんは、ドキュメントを開くに移動します。山口さんは、ファイルがあるを確認できます、松田さんは開けないか、悪意のあるファイルからのコンピューターと他のユーザーを防止するように、共有できません。 
    
ATP の安全な添付ファイルのポリシーは、特定の人または組織内のグループまたはドメイン全体に適用できます。詳細については、 **[Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)** を参照してください。 
  
## <a name="how-to-get-atp-safe-attachments"></a>ATP の安全な添付ファイルを取得する方法

ATP の安全な添付ファイル機能は、高度な脅威保護の Microsoft 365 エンタープライズ、Office 365 のエンタープライズ E5、および Microsoft 365 業務に含まれている部分です。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合は、アドオンとして脅威の高度な保護を購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。
  
場合、安全な添付ファイルの分析ツールの機能に適用されます。
  
- ATP の安全な添付ファイル ポリシーが設定されています。( [Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)を参照してください)。
    
- 職場、学校のアカウントを使用して Office 365 にユーザーに署名します。(詳しくは、 [Office または Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)を参照してください)。
    
### <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>ATP の安全な添付ファイルの保護を確認する方法

 ATP の安全な添付ファイルの保護を配置するためには、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)を定義しなければなりません。 
  
[脅威の高度な保護のためのレポートを表示する](view-reports-for-atp.md)ことでは、サービスの操作方法を表示する方法の 1 つです。
  
さらに、次の表では、いくつかのサンプル シナリオについて説明します。すべてのこれらの場合に、組織には、脅威の高度な保護が含まれています Office 365 エンタープライズ E5 と仮定します。
  
|**シナリオ例**|**ATP の安全な添付ファイルの保護はここで適用しますか。**|
|:-----|:-----|
|Pat の組織の Office 365 のエンタープライズ E5 ですが、ATP の安全な添付ファイルのすべてのポリシーをまだ定義誰が。  <br/> |違います。機能が利用可能ですが、ATP の安全な添付ファイルの保護を配置するために少なくとも 1 つの ATP の安全な添付ファイル ポリシーを定義しなければなりません。  <br/> |
|Contoso の営業部門の従業員です。Lee の組織では、財務部門の従業員のみに適用されるように、ATP の安全な添付ファイル ポリシーがあります。  <br/> |違います。この例では、財務部門の従業員には、ATP の安全な添付ファイルの保護、販売部門を含め、他の従業員は、それらのグループを含むポリシーを定義しなければなりません。  <br/> |
|昨日、ジャンの組織で Office 365 管理者は、すべての従業員に適用される分析ツールの安全な添付ファイル ポリシーを設定します。今日以前のバージョンでは、Jean は、添付ファイルを含む電子メール メッセージを受信します。  <br/> |うん。この例では、ジャンが高度な脅威を保護するためのライセンスを持つし、ジャンが含まれている ATP の安全な添付ファイル ポリシーが定義されています。新しいポリシーを有効にするデータ センターの間を約 30 分がかかります1 日はここで渡される、ため、ポリシーが有効にする必要があります。  <br/> |
|組織では、組織内のすべてのユーザーのために ATP の安全な添付ファイル ポリシーを使用して Office 365 エンタープライズ E5 があります。山口さんは、添付ファイル、および他の組織の外部ユーザーにメッセージを転送する電子メールを受信します。  <br/> |ATP の安全な添付ファイルの保護は、山口さんが受信したメッセージのためには。場合は、受信者の組織 ATP の安全な添付ファイル ポリシーの場所で、し、山口さんに転送するメッセージを対象になるこれらのポリシー転送メッセージが到着するとします。  <br/> |
|森さんの組織 ATP の安全な添付ファイル ポリシーの場所であり、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)は有効にします。青木さんには、SharePoint Online のすべてのファイルをスキャンし、開くか、ダウンロードしても安全ですが想定しています。<br/> |は定義されているポリシーに従って配置では、ATP の安全な添付ファイルの保護ただし、これとは限りません、ビジネス、またはマイクロソフトのチームの OneDrive の SharePoint Online では、すべてのファイルをスキャンすることです。(詳細については、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)を参照してください)。<br/> |
   
## <a name="submitting-files-for-malware-analysis"></a>マルウェアの分析のためのファイルを送信します。

- 分析するためのマイクロソフトを要求するファイルを受信する場合は、[マルウェアの解析用のファイルの送信](https://aka.ms/wdsi/submit)を参照してください。

- 分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を受信する場合、[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。
  
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 の ATP の安全な添付ファイル ポリシーを設定します](set-up-atp-safe-attachments-policies.md)
  
[SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)
  
[Office 365 で ATP の安全なリンク](atp-safe-links.md)
  
[Office 365 の ATP のフィッシング詐欺対策機能](atp-anti-phishing.md)
  
[脅威の高度な保護のためのレポートを表示します。](view-reports-for-atp.md)
  

