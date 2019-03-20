---
title: メールフロールールを使用して Exchange Online Protection で一括メールフィルターを構成する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でのメールフロールールをバルクメールフィルターに使用する方法について説明します。
ms.openlocfilehash: 43f0af6fe41bc7f8f4a62d0d87dbd825fb868f7b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693286"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>メールフロールールを使用して Exchange Online Protection で一括メールフィルターを構成する

既定のスパム コンテンツ フィルター ポリシーを使用して、スパムやバルク メールに対して会社全体のコンテンツ フィルターを設定することができます。コンテンツ フィルター ポリシーを設定する方法については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」と「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps)」を確認してください。 
  
バルクメッセージをフィルター処理するためのその他のオプションが必要な場合は、メールフロールール (トランスポートルールとも呼ばれます) を作成して、バルクメールでよく見られるテキストパターンや語句を検索することができます。 それらの特徴を持つメッセージは、すべてスパムとしてマーク付けされます。 このルールを使用すれば、組織で受信する不要なバルク メールの量を減らすことができます。

> [!IMPORTANT]
> このトピックに記載されているメールフロールールを作成する前に、「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」および「[バルク苦情レベルの値](bulk-complaint-level-values.md)」を参照することをお勧めします。<br>以下の手順は、特定のメッセージを組織全体でスパムとしてマークします。ただし、別の条件を追加すれば、これらのルールを組織内の特定の受信者にだけ適用することができます。このように、積極的なバルク メール フィルター処理設定を注目すべき少数のユーザーにだけ適用することによって、他のユーザー (受信するもののほとんどが登録したバルク メール) には影響を与えないようにすることができます。 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>テキストパターンに基づいてバルクメールメッセージをフィルター処理するメールフロールールを作成する

1. Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. [追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**新しいルールの作成**] を選択します。 **** ![
    
3. ルールの名前を指定します。
    
4. **[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文が次のテキスト パターンと一致する]** の順に選択します。
    
5. **[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の正規表現を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   上記のリストは、バルクメールで検出された正規表現の完全なセットではありません。必要に応じて、追加または削除することができます。 それでも、有益な出発点にはなります。<br>メッセージ内の件名フィールドまたは他のヘッダーフィールドに含まれる単語またはテキストパターンを検索すると、メッセージが ASCII テキスト形式の SMTP サーバー間でバイナリメッセージを送信するために使用された MIME コンテンツ転送エンコード方式からデコードされ*た後*に発生します。 条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。 
    
6. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。
    
7. **[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。
    
   コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。
    
   メッセージを受信者の迷惑メールフォルダーに送信するのではなく、メッセージを検疫するように構成されている場合は、メッセージはメールフロールールの一致として管理者検疫に送信されますが、エンドユーザーのスパム検疫時またはエンドユーザー経由で使用することはできません。スパム通知。 
  
   サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。
    
8. ルールを保存します。
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>メールフロールールを作成して、語句に基づいてバルクメールメッセージをフィルター処理する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. [追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**新しいルールの作成**] を選択します。 **** ![
    
3. ルールの名前を指定します。
    
4. **[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文に次のいずれかの単語を含む]** の順に選択します。
    
5. **[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の語句を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   このリストは、バルクメールで検出された一連の語句を網羅したものではありません。必要に応じて、追加または削除することができます。 それでも、有益な出発点にはなります。
    
6. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。
    
7. **[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。
    
   コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。
    
   メッセージを受信者の迷惑メールフォルダーに送信するのではなく、メッセージを検疫するように構成されている場合は、メッセージはメールフロールールの一致として管理者検疫に送信されますが、エンドユーザーのスパム検疫時またはエンドユーザー経由で使用することはできません。スパム通知。 
  
   サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。

8. ルールを保存します。

## <a name="for-more-information"></a>詳細情報

[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)

[バルク苦情レベルの値](bulk-complaint-level-values.md)

[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)

[高度なスパム対策フィルターオプション](advanced-spam-filtering-asf-options.md)
