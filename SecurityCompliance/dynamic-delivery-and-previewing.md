---
title: 動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: ATP の安全な添付ファイル ポリシーを設定するときに、メッセージの遅延を回避し、スキャンされている添付ファイルをプレビューするのにはユーザーを有効にする動的な配信を選択します。
ms.openlocfilehash: 95c270e871c3febb13eef8c4374d996fc763315b
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769831"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。

**概要**: 動的な配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)を選択できるオプションです。動的な配信および[Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の添付ファイルのプレビュー機能の詳細については、この資料を参照してください。

[ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)組織には電子メールの添付ファイルを処理する方法のいくつかのオプションがあります。**ブロック**、**交換**、および**動的な配信**が含まれます。ATP の安全な添付ファイル ポリシーの構成方法によって、添付ファイルをスキャン中に、電子メールの受信者によってマイナー電子メールの配信に遅延が発生する可能性があります。メッセージの遅延を避けるためには、**動的な配信**を選択します。
  
## <a name="how-dynamic-delivery-works"></a>動的配信のしくみ
  
動的配信では、各電子メールの添付ファイルのプレース ホルダーを持つ受信者に、電子メール メッセージの本文を送信することによりメールの遅延を排除します。プレース ホルダーは、添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が安全であると判断されるまで残ります。 

- 各添付ファイルをオフにすると、開くか、ダウンロードに使用可能です。 

- 悪意のある添付ファイルが確認された場合、検疫に送信されます、 [Office 365 で検疫されたメッセージを管理する](manage-quarantined-messages-and-files.md)ことができます (Office 365 のグローバル管理者またはセキュリティ管理者の場合) などの組織のセキュリティ チームの他の場所。

ほとんどの Pdf や Office が進行中で ATP のスキャン中に、セーフ モードでドキュメントをプレビューできます。添付ファイルに動的な配信プレビュー用のプログラムと互換性がない場合電子メールの受信者は、ATP の安全な添付ファイルのスキャンが完了するまでに、添付ファイルのプレース ホルダーが参照してください。

動的配信では、読み取り、および、添付ファイルを分析しているときに、電子メール メッセージにすぐに応答します。 

スキャンでは、ATP 安全な添付ファイルを Office 365 のデータが格納されている同じ地域に配置します。データ センターの地理的条件の詳細についてを参照してください[にあるデータがあるか?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>添付ファイルを含む電子メールを転送他のときの動作ですか。

組織が、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の動的な配信を使用して添付ファイルを含む電子メールを受け取る他のユーザーとします。今すぐその人が他のユーザーに電子メール メッセージを転送します。どうなりますか。ATP の安全な添付ファイル ポリシーに追加の受信者が含まれているかどうかによって異なります。
  
- 場合は受信者が動的な配信オプションを使用して、ATP の安全な添付ファイル ポリシーの対象でし、受信者が表示されるプレース ホルダーは、互換性のあるファイルをプレビューする機能を持つ。
    
- 場合は、受信者は、ATP の安全な添付ファイル ポリシーの影響を受けません、電子メールと添付ファイルは進み、ATP スキャン安全な添付ファイルや添付ファイルのプレース ホルダーです。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>動作する動的な配信に必要となるものですか。

- 組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持つ必要があります。
    
- ATP (を参照してください[Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)) の動的な配信オプションを使用して安全な添付ファイルのポリシーを定義する必要があります。
    
- Office 365 で、組織の電子メールをホストする必要があります。
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>動的な配信が利用可能ないないシナリオはありますか。

動的な配信がサポートされていない特定のシナリオがあります。これらを以下に示します。
  
- 電子メール メッセージをパブリック フォルダーに含まれる
    
- 電子メールをルーティングし、カスタム規則を使用してユーザーのメールボックスには、
    
- 電子メール メッセージは、(自動または手動) をホストされているメールボックスとアーカイブのフォルダーを含む、他の場所に移動します。
    
- 電子メール メッセージを削除します。
    
- エラー状態では、ユーザーのメールボックスの検索フォルダー
    
- Exclaimer Exchange Online 管理者が有効にする環境。この問題を解決するには、 [ATP の動的な配信および Exclaimer を使用すると、添付ファイル付きのメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)を参照してください.

- [/Multipurpose をセキュリティで保護されたインターネット メール拡張 (S/MIME)](s-mime-for-message-signing-and-encryption.md)で暗号化されたメッセージ)
    
