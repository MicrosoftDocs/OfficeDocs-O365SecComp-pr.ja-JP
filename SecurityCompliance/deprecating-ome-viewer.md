---
title: 廃止 Office 365 Message Encryption Viewer アプリ
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 2018年8月15日には、Office 365 Message Encryption (OME) Viewer モバイルアプリを Android および Apple ストアから削除します。 以前のバージョンの OME で Apple と Android の電話機で暗号化された電子メールメッセージと添付ファイルを読み取るには、Office 365 Message Encryption Viewer モバイルアプリが必要でした。 OME Viewer アプリの削除とは別に、以前のバージョンの OME には他の変更は加えていません。
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153349"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>廃止 Office 365 Message Encryption Viewer アプリ

2018年8月15日に、Office 365 Message Encryption (OME) Viewer モバイルアプリが Android および Apple ストアから削除されました。 以前のバージョンの OME で Apple と Android の電話機で暗号化された電子メールメッセージと添付ファイルを読み取るには、Office 365 Message Encryption Viewer モバイルアプリが必要でした。 OME Viewer アプリの削除とは別に、以前のバージョンの OME には他の変更は加えていません。
  
## <a name="changes-from-august-2018"></a>2018年8月の変更

2017年9月に発表されたように、microsoft は新しいバージョンの[Office 365 Message Encryption](https://aka.ms/ome2017)をリリースしました。これにより、ユーザーは、暗号化されたメッセージと保護されたメッセージを、モバイルアプリの要件なしに、組織内外のユーザーに送信できます。 その後、追加機能が追加されました。
  
- [暗号化専用テンプレート](https://aka.ms/encryptonly)

- [添付ファイルの暗号化を解除するコントロール](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
この変更により、ユーザーは8月1日までに Office 365 Message Encryption Viewer モバイルアプリをダウンロードできなくなります。 その結果、メールの受信者は、一部の Android および Apple モバイルデバイスで、以前のバージョンの OME で暗号化されたメッセージを読むことができない場合があります。 ただし、これらのメッセージをパーソナルコンピューター (デスクトップブラウザー経由) で読み取ることはできます。 既にアプリをダウンロードしているユーザーは、引き続きそのアプリを使用できるようになります。
  
## <a name="why-this-change-was-made"></a>この変更が行われた理由

新しいバージョンの OME では、モバイルアプリで保護された電子メールメッセージと添付ファイルを読み取る必要がなくなりました。 Office 365 新しい OME 機能を使用しているお客様は、保護されたメッセージを Outlook mobile および非 Office 365 で表示できます。ユーザーは、保護されたメッセージをブラウザーで表示できます。
  
ユーザーが保護されたメッセージを表示できるようにするために、ユーザーにモバイルアプリのダウンロードを要求する hurdle があります。 新しい Office 365 メッセージの暗号化機能は、より優れたモバイル環境を提供します。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンの Office 365 メッセージの暗号化を引き続き使用することができます。

以前のバージョンの Office 365 メッセージの暗号化は、現時点では推奨されていません。ただし、新しいバージョンの Office 365 Message Encryption には大幅な機能強化が加えられているため、機密データを暗号化して他のユーザーに保護することが容易になります。および任意のデバイス (Office 365 ユーザーが保護されたメッセージを Outlook (デスクトップ、モバイル、および web) で直接読み取る機能を含む)。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>この変更を準備するために必要な作業

組織が暗号化された添付ファイルを OME Viewer アプリを必要とする受信者に現在送信している場合は、ドキュメントとトレーニングリソースを更新する必要があります。
  
既存の Exchange メールフロールールを更新して現在のバージョンの OME を使用することをお勧めします。これにより、組織は新機能と強化された機能を活用できるようになります。 OME の新しい機能を設定すると、受信者はモバイルデバイスで暗号化されたメッセージを読み取るために OME ビューアアプリを必要としなくなります。
  
Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。 手順については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。 新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。
  

