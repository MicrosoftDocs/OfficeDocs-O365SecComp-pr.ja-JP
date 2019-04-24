---
title: トラブルシューティングとサポート情報
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。
ms.openlocfilehash: bea2ad502f24d63874bfa954e6d67c73dc44d98d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259845"
---
# <a name="troubleshooting-and-support-information"></a>トラブルシューティングとサポート情報

このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。
  
## <a name="troubleshooting-for-users"></a>ユーザー向けのトラブルシューティング

迷惑メール報告アドインの追加後に、Microsoft Office Outlook で問題が発生することがあります。発生する可能性のある問題とそれらの問題を解決するためのヒントを以下に示します。 
  
- **[迷惑メールの報告]** をクリックしても何も起こらない
    
- 電子メール メッセージを選択した後に Outlook が応答しなくなった
    
- "配信不能" と返され、報告された迷惑メールを配信できない
    
### <a name="troubleshooting-tip"></a>トラブルシューティングのヒント

1. Microsoft Office Outlook を終了して再起動します。
    
2. テスト メッセージを作成して、送信できることを確認します。これを実行するには、テスト メッセージを自分が管理する別の電子メール アカウントに送信し、電子メール メッセージが受信されることを確認します。
    
問題が引き続き発生する場合は、IT 管理者に問い合わせてください。
  
> [!TIP]
> また [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) 宛てにレポートを送信し、Microsoft に直接スパム メッセージを報告することもできます。さらに、誤検知のメッセージについては [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) の電子メール アドレスに報告できます。詳細については、「 [スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。 
  
## <a name="troubleshooting-for-administrators"></a>管理者向けのトラブルシューティング

管理者は、Microsoft Office Outlook 用迷惑メール報告アドインを使用しているユーザーの問題に対処する場合があります。以下に、発生する可能性のある問題を解決するためのヒントを示します。 
  
 **問題:** ユーザーにシステム管理者に問い合わせるよう要求するエラー メッセージが連続して表示される。 
  
### <a name="troubleshooting-tip"></a>トラブルシューティングのヒント

1. 次のレジストリ キーの値を "Verbose" に設定します。
    
  - **32 ビット オペレーティング システムにインストールされている 32 ビット Outlook:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64 ビット オペレーティング システムにインストールされている 32 ビット Outlook:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64 ビット Outlook (必ず 64 ビット オペレーティング システムにインストールされる):**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. Microsoft Office Outlook を再起動し、エラー メッセージが表示されたら報告するようユーザーに依頼します。
    
3. 次の場所にあるログ情報を収集します。 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。 
    
 **問題:** ユーザーが迷惑メールとして電子メールを送信したときに確認を受信しないよう選択したが、現在、そのオプションを元に戻すことを希望している。 
  
### <a name="troubleshooting-tip"></a>トラブルシューティングのヒント

1. 次のレジストリ キーの値を "True" に設定します。HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. Microsoft Office Outlook を再起動します。
    
## <a name="support-information"></a>サポート情報

アドインのインストール、構成、またはアンインストールに関してサポートが必要な場合は、Microsoft 365 管理センターのサポートページにある [新しいサービスリクエスト] リンクを使用してテクニカルサポートにお問い合わせください。 電話およびセルフサポートオプション経由でのサービス要求の提出などのその他のオプションについては、「 [Help and support for EOP](eop/help-and-support-for-eop.md)」を参照してください。
  
## <a name="for-more-information"></a>関連情報

[レポート メッセージ アドインを有効にする](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[迷惑メール メッセージを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)
  

