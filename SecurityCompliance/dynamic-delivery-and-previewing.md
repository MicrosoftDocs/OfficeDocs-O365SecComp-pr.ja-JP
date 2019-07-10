---
title: Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: ATP の安全な添付ファイルのポリシーを設定する場合は、[動的配信] を選択してメッセージの遅延を回避し、スキャンされた添付ファイルをプレビューできるようにします。
ms.openlocfilehash: 2f965c119e9c4fca15e43d281dfc2d00d2c79c23
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599903"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル

## <a name="overview"></a>概要

動的配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)に対して選択可能なオプションです。 この記事では、 [Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の動的配信および添付ファイルのプレビュー機能について説明します。

組織に対して[ATP の安全な添付ファイルポリシーが設定さ](set-up-atp-safe-attachments-policies.md)れている場合は、電子メールの添付ファイルの処理方法に関するいくつかのオプションがあります。 これには、**ブロック**、**置換**、および**動的配信**が含まれます。 ATP の安全な添付ファイルポリシーの構成によっては、電子メールの受信者が、添付ファイルがスキャンされている間、電子メール配信に多少の遅延が発生する可能性があります。 メッセージの遅延を回避するには、[**動的配信**] を選択します。
  
## <a name="how-dynamic-delivery-works"></a>動的配信のしくみ
  
動的配信では、電子メールの添付ファイルごとにプレースホルダーを使用して電子メールメッセージの本文を受信者に送信することによって、メールの遅延を排除します。 添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)によって安全であると判断されるまで、プレースホルダーは残ります。 

- 各添付ファイルが削除されると、その添付ファイルを開いたりダウンロードしたりできます。 

- 添付ファイルが悪意のあるものと判断された場合は、検疫に送信されます。これにより、組織のセキュリティチーム (Office 365 のグローバル管理者やセキュリティ管理者など) が[office 365 の検疫済みメッセージを管理](manage-quarantined-messages-and-files.md)できるようになります。

ほとんどの Pdf および Office ドキュメントは、ATP のスキャンが進行している間、セーフモードでプレビューできます。 添付ファイルが動的配信プレビューアーに対応していない場合、電子メールの受信者には、ATP の安全な添付ファイルのスキャンが完了するまで、添付ファイルプレースホルダーが表示されます。

> [!TIP]
> モバイルデバイスを使用していて、初めて動的配信プレビューで Pdf が表示されない場合は、モバイルブラウザーを使用して Office 365 にサインインしてください。

動的配信を使用すると、ユーザーはすぐに電子メールメッセージの読み取りと応答を行うことができますが、添付ファイルは分析されます。 

ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。 データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>添付ファイルを含む電子メールを他のユーザーが転送した場合はどうなりますか。

組織が[ATP の安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)の動的配信を使用していて、誰かが添付ファイルを含む電子メールを受信したとします。 そのユーザーが電子メールメッセージを他のユーザーに転送したとします。 どうなりますか? これは、追加の受信者が ATP の安全な添付ファイルポリシーに含まれているかどうかによって異なります。
  
- [動的配信] オプションを使用して、受信者が ATP の安全な添付ファイルポリシーでカバーされている場合、受信者には、互換性のあるファイルをプレビューできるプレースホルダーが表示されます。
    
- 受信者が ATP の安全な添付ファイルポリシーでカバーされていない場合、電子メールと添付ファイルは、ATP の安全な添付ファイルのスキャンまたは添付ファイルのプレースホルダーを使用せずに実行されます。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>動的配信が機能するために必要なこと

- 組織が[Office 365 Advanced Threat Protection](office-365-atp.md)を持っている必要がある
    
- [動的配信] オプションを使用して、ATP の安全な添付ファイルに関するポリシーを定義する必要があります (「 [Office 365 の atp の安全な添付ファイルポリシーの設定](set-up-atp-safe-attachments-policies.md)」を参照)。
    
- 組織の電子メールは、Office 365 でホストされている必要があります。 [どの SMTP メール転送エージェント (Exchange Server など) でも Office 365 Advanced Threat Protection を使用でき](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)ますが、ATP の安全な添付ファイルの動的配信オプションでは、組織の電子メールが Office 365 でホストされている必要があります。 メールが Office 365 でホストされていない場合は、[**ブロック**] などの別の[ATP の安全な添付ファイルポリシーオプション](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)を選択します。
    
## <a name="additional-considerations"></a>その他の考慮事項

動的配信はサポートされていない特定のシナリオがあります。 これらには次のコマンドレットがあります。
  
- パブリックフォルダー内の電子メールメッセージ
    
- カスタムルールを使用して、ユーザーのメールボックスにルーティングされてから戻る電子メールメッセージ
    
- ホストされたメールボックスと、アーカイブフォルダーなどの他の場所に移動した (自動または手動で) 電子メールメッセージ
    
- 削除された電子メールメッセージ
    
- エラー状態にあるユーザーのメールボックス検索フォルダー
    
- Exchange Online 管理者が Exclaimer を有効にしている環境。 この解決方法については、「 [ATP Dynamic Delivery And Exclaimer の使用時に添付ファイル付きメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)」を参照してください。

- [セキュリティで保護された、または汎用インターネットメール内線 (S/MIME)](s-mime-for-message-signing-and-encryption.md)で暗号化されたメッセージ

- 動的配信がサポートされていない場合、ATP の安全な添付ファイルは電子メールメッセージをスキャンしません。 ただし、 [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)がどのように構成されているかに応じて、url を含む添付ファイル付きの電子メールメッセージを配信することが確認されます。 このような場合、電子メールメッセージと Office ファイルの Url がチェックされます。
