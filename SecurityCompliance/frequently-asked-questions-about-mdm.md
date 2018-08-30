---
title: Office 365 でモバイル デバイスの管理についてよく寄せられる質問
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3871f99c-c9db-4a23-86f9-902c1b02f58d
description: この資料には、Office 365 を管理し、Office 365 でモバイル デバイスをセキュリティで保護するために役立つ機能についてのよく寄せられる質問については、モバイル デバイス管理 (MDM) が含まれています。
ms.openlocfilehash: 6c4a5b3603d392b3d83769cd0f17450ce70565be
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272272"
---
# <a name="frequently-asked-questions-about-mobile-device-management-for-office-365"></a>Office 365 でモバイル デバイスの管理についてよく寄せられる質問

この資料には、Office 365 を管理し、Office 365 でモバイル デバイスをセキュリティで保護するために役立つ機能についてのよく寄せられる質問については、モバイル デバイス管理 (MDM) が含まれています。
  
## <a name="faqs"></a>FAQ

- [Office 365 の MDM を取得する方法は?Office 365 の管理ページに表示されません。](#how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center)
    
- [どのように取り掛かることができるか MDM のデバイス管理](#how-can-i-get-started-with-device-management-in-mdm)
    
- [MDM を設定しようとしていますが、詰まっているように思えます。Office 365 サービスの稼働状態が表示されて、しばらくの間には、「プロビジョニング」。どうすればいいんでしょうか。](#im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do)
    
- [デバイスの登録に失敗した場合の何か。](#what-can-i-do-if-device-enrollment-fails)
    
- [Intune と Office 365 の MDM の違いは何ですか。](#whats-the-difference-between-intune-and-mdm-for-office-365)
    
- [MDM のポリシーの動作方法それらを設定する方法それらを無効にしますか。](#how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them)
    
- [私に切り替えることが Exchange ActiveSync のデバイス管理から MDM Office 365 のでしょうか。](#can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365)
    
- [MDM を設定するには、それを削除するようになりました。手順は?](#i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps)
    
- [ヘルプが必要](#still-need-help)
    
## <a name="how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center"></a>Office 365 の MDM を取得する方法は?Office 365 の管理ページに表示されません。

Office 365 のお客様にこの機能を展開が終了しました。[**デバイスの管理**] タブの[には、Office 365 のセキュリティ&amp;コンプライアンス センター](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)です。場合は表示されない場合は、知らせてください。参照してください[ヘルプが必要ですか?](#still-need-help)を使い始めることをお手伝いします。 
  
## <a name="how-can-i-get-started-with-device-management-in-mdm"></a>どのように取り掛かることができるか MDM のデバイス管理

Office 365 の ([設定をモバイル デバイス管理 (MDM) では、Office 365](set-up-mobile-device-management.md)の詳細については) の MDM を始める前に次の 4 つの手順です。
  
1. **MDM. をアクティブにします。**[には、Office 365 のセキュリティ&amp;コンプライアンス センター](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) **デバイスの管理**] を選択するとします。**では**ライセンス認証プロセスを開始する] をクリックします。 
    
2. **MDM の構成を完了**します。ドメインの Apn の証明書の構成と DNS レコードの更新が必要です。 
    
3. **ポリシーを作成**します。デバイス管理ポリシーを作成し、[セキュリティ グループで設定](create-device-security-policies.md)されたユーザーのグループに適用します。小規模なテスト グループにポリシーを展開することによって開始することをお勧めします。セキュリティ&amp;コンプライアンス センターでは、**デバイスのセキュリティ ポリシー**を選択します。
    
4. **ユーザーがデバイスを登録します**。(たとえば、電子メール クライアントを使用して)、Office 365 のデータにアクセスしようとすると、それらに適用されるポリシーを持っているユーザーが[、デバイスを登録](enroll-your-mobile-device.md)するよう求められます。 
    
## <a name="im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>MDM を設定しようとしていますが、詰まっているように思えます。Office 365 サービスの稼働状態が表示されて、しばらくの間には、「プロビジョニング」。どうすればいいんでしょうか。

サービスを準備するまでにしばらく時間がかかる場合があります。プロビジョニングが完了すると、Office 365 のページのモバイル デバイスの管理が表示されます。24 時間を待機するいるし、**プロビジョニング**ステータスを参照してください[ヘルプが必要ですか?](#still-need-help)し、問題とは何がお手伝いします。 
  
## <a name="what-can-i-do-if-device-enrollment-fails"></a>デバイスの登録に失敗した場合の何か。

デバイスの登録に問題がある場合は、まず以下を確認してください。
  
- そのデバイスは既に登録していない Intune など、他のモバイル デバイス管理プロバイダーに確認します。
    
- デバイスが、正しい日付と時刻に設定されていることを確認します。
    
- 別の Wi-fi または携帯電話のネットワーク デバイス上に切り替えます。
    
- Android や iOS デバイスでは、アンインストールし、Intune 会社のポータル アプリケーションを再インストール、デバイスにします。
    
登録がまだの場合に動作していない、[追加のトラブルシューティング手順を実行してください](troubleshoot-mdm.md)。
  
## <a name="whats-the-difference-between-intune-and-mdm-for-office-365"></a>Intune と Office 365 の MDM の違いは何ですか。

Office 365 と Intune の両方の MDM は、組織内のデバイスを管理するためのクラウド ベースのソリューションを提供します。Intune または MDM を使用して、Office 365 がするの最適かを判断するのにには、2 つのサービスの[横に並べて比較](choose-between-mdm-and-intune.md)を使用します。 
  
## <a name="how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them"></a>MDM のポリシーの動作方法それらを設定する方法それらを無効にしますか。

[ポリシーを作成しユーザーのグループに適用](create-device-security-policies.md)では、Office 365 の MDM の初期セットアップを完了した後[には、Office 365 のセキュリティ&amp;コンプライアンス センター](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)です。ポリシーが適用されるユーザー ポリシーはユーザーが Office 365 のデータにアクセスするデバイスを使用するには、Office 365 の MDM では、そのデバイスを登録する必要があります。ポリシーを設定することは、例では、どのくらいの頻度のパスワードをリセットする必要がありますまたはデータの暗号化が必要かどうか、モバイル デバイスの設定を確認します。 
  
[作成する](create-device-security-policies.md)と、デバイスのセキュリティ ポリシーを展開する手順を提供しています。セキュリティ ポリシーを作成する&amp;コンプライアンスの中心とすることができますセキュリティを返すことによって 1 つまたは複数のポリシーを無効にする&amp;適用されているグループを削除するのにはコンプライアンスの中心とポリシーを編集します。またはポリシーを完全に削除しないように選択することができます。
  
ポリシーによって影響を受けるから特定のユーザー グループを除外する場合は、除外グループにグループを追加できます。セキュリティ&amp;コンプライアンス センター] の [**デバイス**] タブで、**デバイスのアクセス設定の管理**] を選択し、グループを**アクセス制御から除外するすべてのセキュリティ グループではないですか?** セクション。 
  
## <a name="can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365"></a>私に切り替えることが Exchange ActiveSync のデバイス管理から MDM Office 365 のでしょうか。

モバイル デバイスを管理するために[Exchange ActiveSync ポリシー](https://go.microsoft.com/fwlink/?LinkId=615145)を使用して、設定[をモバイル デバイス管理 (MDM) Office 365 の](set-up-mobile-device-management.md)手順を実行して Office 365 の MDM を使用を開始できます。
  
MDM のグループのユーザーを Office 365 に作成したポリシーを適用すると、これらのポリシーは、Exchange ActiveSync モバイル デバイス メールボックス ポリシーとそれらのユーザーの Exchange 管理センターで以前作成したデバイスのアクセス規則をオーバーライドします。 
  
デバイスが Exchange ActiveSync モバイル デバイス メールボックス ポリシーを使用すると、Office 365 の MDM に登録されているか、デバイスに適用するデバイス アクセス ルールは無視されます。
  
## <a name="i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps"></a>MDM を設定するには、それを削除するようになりました。手順は?

残念ながら、ことはできません単に"提供を解除する「MDM Office 365 の設定した後です。デバイス ポリシーを作成したユーザー セキュリティ グループを削除することによってユーザーのグループにそれを削除することが。またはに配置されていないし、適用されていないデバイスのポリシーを削除することによってすべてのユーザーに対して無効にします。[Office 365 でモバイル デバイスの管理を無効にする方法](turn-off-mdm.md)を参照してください。
  
## <a name="still-need-help"></a>ヘルプが必要ですか。

[![Office 365 コミュニティ フォーラムからヘルプを取得する](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理者:サインインしてサービス リクエストを作成する](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理者:サポートの依頼](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

  

