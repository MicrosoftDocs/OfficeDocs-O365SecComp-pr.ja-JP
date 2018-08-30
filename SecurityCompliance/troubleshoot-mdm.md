---
title: Office 365 の MDM のデバイスの登録のトラブルシューティングを行う
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: Office 365 のデバイスでモバイル デバイス管理 (MDM) を登録しようとするときの問題に実行している場合、は、以下の手順に従って問題を追跡するためをしてください。一般的な手順で問題が解決しない場合、デバイス ・ タイプの特定の手順を実行後のセクションのいずれかを参照してください。
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272112"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a>Office 365 の MDM のデバイスの登録のトラブルシューティングを行う

Office 365 のデバイスでモバイル デバイス管理 (MDM) を登録しようとするときの問題に実行している場合、は、以下の手順に従って問題を追跡するためをしてください。一般的な手順で問題が解決しない場合、デバイス ・ タイプの特定の手順を実行後のセクションのいずれかを参照してください。
  
## <a name="steps-to-try-first"></a>最初に手順を実行します。

開始するには、次の手順を確認します。
  
- そのデバイスは既に登録していない Intune など、他のモバイル デバイス管理プロバイダーに確認します。
    
- デバイスが、正しい日付と時刻に設定されていることを確認します。
    
- 別の Wi-fi または携帯電話のネットワーク デバイス上に切り替えます。
    
- Android や iOS デバイスでは、アンインストールし、Intune 会社のポータル アプリケーションを再インストール、デバイスにします。
    
## <a name="ios-phone-or-tablet"></a>iOS の携帯電話やタブレット

- [Apn の証明書を設定](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)したりしたことを確認します。
    
- **設定**で\>**一般的な** \> **プロファイル**(または**デバイスの管理**) では、**管理プロファイル**が既にインストールされていないことを確認します。場合は、それを削除します。 
    
- 「に登録して、デバイスが失敗しました」エラー メッセージが表示される場合は、Office 365 にサインインし、デバイスにサインインしたユーザーを含む Exchange Online ライセンスが割り当てられているかどうかを確認します。
    
- 「プロファイルをインストールするに失敗しました」エラー メッセージが表示される場合は、次のいずれかを試してください。
    
  - Safari が、デバイスの既定のブラウザーであること、および cookie が無効になっていないことを確認ください。
    
  - 、デバイスを再起動し、portal.manage.microsoft.com に移動、Office 365 のユーザー ID とパスワードでサインイン、プロファイルを手動でインストールしようとしてください。
    
## <a name="windows-rt-tablet"></a>Windows RT タブレット

- ドメインには、 [MDM を使用する Office 365 のセットアップ](set-up-mobile-device-management.md)を確認します。
    
- **オンにする**を選択することがなく、ユーザー**への参加**を選択するようにしてください。
    
## <a name="windows-phone"></a>Windows Phone

- ドメインには、 [MDM を使用する Office 365 のセットアップ](set-up-mobile-device-management.md)を確認します。
    
- デバイスで Windows 8.1 以降を実行することを確認します。
    
## <a name="android-phone-or-tablet"></a>Android の携帯電話やタブレット

- 4.0 またはそれ以降、デバイスは Android を実行していることを確認します。
    
- 「このデバイスでは、私たち登録できませんでした」エラー メッセージが表示される場合は、Office 365 にサインインし、、デバイスにサインインしたユーザーを含む Exchange Online ライセンスが割り当てられているどうかを確認します。
    
- 必要なエンドユーザー操作が保留中、かどうかをデバイスに**通知領域**を確認し、場合は、操作を完了します。 
    

