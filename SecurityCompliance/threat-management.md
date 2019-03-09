---
title: Threat management in the Office 365 Security &amp; Compliance Center
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
ms.collection:
- M365-security-compliance
description: 脅威管理を使用して、組織のデータへのモバイルデバイスアクセスの制御と管理、データ損失からの組織の保護、および悪意のあるソフトウェアとスパムからの受信および送信メッセージの保護に役立ちます。 また、脅威管理を使用して、ドメインの評価を保護し、送信者が悪意のあるドメインからのアカウントを偽装しているかどうかを判断します。
ms.openlocfilehash: d3a9b688e12ec2c1a8c6ddabbdcd881f4c3e0bda
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492846"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Threat management in the Office 365 Security &amp; Compliance Center

脅威管理を使用して、組織のデータへのモバイルデバイスアクセスの制御と管理、データ損失からの組織の保護、および悪意のあるソフトウェアとスパムからの受信および送信メッセージの保護に役立ちます。 また、脅威管理を使用して、ドメインの評価を保護し、送信者が悪意のあるドメインからのアカウントを偽装しているかどうかを判断します。
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターで脅威管理を表示および使用する方法

Office 365 で、セキュリティ&amp;コンプライアンスセンターを使用して組織内の脅威を管理します。
  
 **セキュリティ&amp; /コンプライアンスセンターに直接移動するには、次のようにします。**
  
1. [https://protection.office.com](https://protection.office.com) に移動します。

2. 職場または学校のアカウントを使用して、Office 365 にサインインします。

3. 左側のウィンドウで、[**脅威の管理**] を選択します。

    ![Office 365 セキュリティ&amp;コンプライアンスセンターの脅威管理メニュー](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **Office 365 アプリ起動ツール&amp;を使用してセキュリティコンプライアンスセンターに移動するには、次のようにします。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. ![左上隅にある Office 365](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)のアプリ起動ツールのアイコンを選択し、[ ** &amp;セキュリティコンプライアンス**] タイルを選択します。 

3. 左側のウィンドウで、[**脅威の管理**] を選択します。

## <a name="about-threat-management-in-office-365"></a>Office 365 での脅威管理について

これらのオプションは、セキュリティ&amp;コンプライアンスセンターの**脅威管理**の下で利用できます。
  
セキュリティ&amp;コンプライアンスセンターの脅威管理はまだ展開されていないため、これらのすべてが表示されないかもしれません。また、ここにリストされているオプションよりも多くのことがわかります。 このような場合、マルウェア対策、dkim などの一部は、公開時に、Exchange 管理センター (EAC) を使用して一定の時間だけ使用できます。

場合によっては、EAC とセキュリティ&amp; /コンプライアンスセンターの実装の間に小さな違いがあります。 たとえば、スパムフィルターでサポートされている文字は、2つのプラットフォーム間で異なります。 記事は、発生時に特定の違いに関する詳細情報を提供します。
  
|**ツール**|**説明**|
|:-----|:-----|
|**ダッシュボード、脅威エクスプローラー、およびインシデント** <br/> |有効にすると、これらのウィンドウを使用して Office 365 Analytics および脅威インテリジェンスを管理できます。 詳細については、「 [Office 365 脅威インテリジェンスの概要](office-365-ti.md)」を参照してください。  <br/> |
|**メールフィルター** <br/> |Office 365 でスパムを防止するための設定を微調整し、監視します。 許可と禁止の一覧を作成し、ドメインをスプーフィングしているユーザーとその理由を特定し、スパムフィルターポリシーを構成および表示します。 詳細については、「 [Office 365 電子メールのスパム対策保護](anti-spam-protection.md)」を参照してください。  <br/> また、ユーザーがスパムを送信していないことを確認するポリシーを設定することもできます。 これは、たとえば、ユーザーのコンピューターが、電子メールメッセージを送信するようにプログラムされたマルウェアに感染した場合に発生する可能性があります。 送信スパムを防ぐ方法については、「 [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)」を参照してください。  <br/> 現在、スパムに関する問題が発生している場合は、[スパムおよびマルウェアのトラブルシューティングツール](https://configure.office.com/Scenario.aspx?sid=73)を使用できます。           |
|**マルウェア対策** <br/> |Office 365 で、組織との間でウイルスやスパイウェアから保護されます。 ウイルスは、実行時に自分自身をレプリケートし、コンピューター上の他のプログラムやデータを変更する、悪意のあるソフトウェアプログラムです。 ウイルスは感染したプログラムを検索していますが、コンピューター間で感染することもあります。 スパイウェアは、サインイン情報などの個人情報を収集し、作成者に送り返します。 マルウェア対策ポリシーの構成を開始するには、「[マルウェア対策ポリシーを構成](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx)する」を参照してください。  <br/> 現在、マルウェアの問題が発生している場合は、[スパムおよびマルウェアのトラブルシューティングツール](https://configure.office.com/Scenario.aspx?sid=73)を使用できます。           |
|**DKIM** <br/> |office 365 の高度な管理者を対象としていますが、すべての office 365 のお客様、domainkeys が特定されたメール (dkim) を使用して、office 365 から送信したメッセージを他の電子メールシステムが信頼するようにすることができます。 dkim では、組織から送信した電子メールメッセージに一意のデジタル署名を追加することによって、これを行います。 から電子メールを受信する電子メールシステムこのデジタル署名を使用して、電子メールが正当であるかどうかを判断できます。  <br/> 多くの組織では、Office 365 で設定されている既定の機能を使用できるようになるため、この動作の詳細がどうなっているかは心配しないでください。 自分で dkim をセットアップしない場合、Office 365 は、自分のドメインに対して dkim を有効にするために作成される既定のポリシーとキーを使用します。 また、dkim 署名を無効にすると、一定の期間が経過すると、office 365 によって自動的に office 365 の既定のポリシーがドメインに対して有効になります。  <br/> 必要に応じて、このページをセキュリティ&amp;コンプライアンスセンターで表示し、現在のドメインに対して dkim 署名が現在有効になっているかどうかを確認し、Office 365 で使用された暗号化キーがローテーションされた最後の時刻を表示することができます。 手動でキーを回転することもできます。  <br/> **大事な！** dkim は、Office 365 で使用される電子メール認証手法は1つだけです。 最も効果的になるように、dkim は Sender Policy Framework (SPF)、ドメインベースのメッセージ認証、レポート、準拠 (DMARC) など、サポートされている他の手法と共に使用されます。 これらのドメインベースの認証テクノロジを組み合わせると、スパムや不要なスプーフィングを防止することができます。<br/>  セキュリティ&amp; /コンプライアンスセンターを使用して dkim を変更する前に、このテクノロジに慣れることができます。また、それがどのように機能するかを理解することができます。 最初に、「 [Office 365 でスパムを防ぐ方法」の基本事項](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)を参照してください。           |
|**安全な添付ファイル**<br/>|「[安全な添付ファイル](atp-safe-attachments.md)」は Advanced Threat Protection の一部です。 有効にした場合、電子メールの添付ファイルは、Office 365 とは別の、受信者の受信トレイに送信される前の専用の分離された環境で開きます。 「安全な添付ファイル」は、ウイルス対策の署名を使用できるようになる前でも、悪意のある添付ファイルを検出するために設計されて 詳細については、「 [Office 365 の安全な添付ファイル](atp-safe-attachments.md)」を参照してください。<br/> |
|**安全なリンク** <br/> |「[安全なリンク](atp-safe-links.md)」は Advanced Threat Protection の一部です。 安全なリンクによって、ユーザーが電子メールや悪意のある web サイトを指す Office ドキュメントで url をフォローするのを防ぐことができます。 詳細については、「 [Office 365 の安全なリンク](atp-safe-links.md)」を参照してください。<br/> |
|**検疫**<br/>|Office 365 で受信メールメッセージの[検疫](http://go.microsoft.com/fwlink/p/?LinkID=809005)を設定するスパム、バルク、フィッシング、マルウェアメールとしてフィルター処理されたメッセージは、後で確認するために保持できます。 ユーザーと管理者の両方が、検疫済みメッセージを操作できます。 ユーザーは、隔離された独自のフィルター処理されたメッセージのみを操作できます。 管理者は、すべてのユーザーの検疫済みメッセージを検索し、管理することができます。  <br/> |
|**高度な脅威** <br/> |[脅威保護の状態レポート](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats)を表示して、Exchange Online Protection と Advanced Threat protection によって検出されブロックされた、悪意のあるコンテンツに関する情報を表示します。  <br/> |
