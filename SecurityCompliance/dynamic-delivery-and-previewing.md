---
title: 動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: ATP の安全な添付ファイル ポリシーを設定するときに、メッセージの遅延を回避し、スキャンされている添付ファイルをプレビューするのにはユーザーを有効にする動的な配信を選択します。
ms.openlocfilehash: 23017f4f995dfe6a90479d83af9522531d7bf96b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531554"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。

動的な配信を選択できるオプションです。動的な配信および[Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の添付ファイルのプレビュー機能の詳細については、この資料を参照してください。
  
## <a name="how-dynamic-delivery-works"></a>動的配信のしくみ

[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)すると、選択できます**ブロック**、**交換**をには、**動的な配信**など、いくつかのオプションから。ポリシーの構成方法によって、添付ファイルをスキャン中に、電子メールの受信者によって電子メールの配信に小さな遅延が発生することができます。メッセージの遅延を避けるためには、**動的な配信**を選択します。
  
動的な配信オプションは、各電子メールの添付ファイルのプレース ホルダーを使用した電子メール メッセージの本文を送信することによりメールの遅延を排除します。プレース ホルダーは、添付ファイルが[Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)がスキャンされるまで残ります。電子メールの受信者は、読み取りおよび応答の電子メール メッセージをすぐにその添付ファイルを分析していることを知ることです。
  
ほとんどの Pdf や Office が進行中で ATP のスキャン中に、セーフ モードでドキュメントをプレビューできます。添付ファイルに動的な配信プレビュー用のプログラムと互換性がない場合電子メールの受信者は、ATP の安全な添付ファイルのスキャンが完了するまでに、添付ファイルのプレース ホルダーが参照してください。
  
各添付ファイルがオフになって、元の電子メール メッセージに自動的に再アタッチします。悪意のある添付ファイルが確認された場合、検疫に送信されます、 [Office 365 で検疫されたメッセージを管理する](manage-quarantined-messages-and-files.md)ことができます (Office 365 のグローバル管理者またはセキュリティ管理者の場合) などの組織のセキュリティ チームの他の場所。
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>添付ファイルを含む電子メールを転送他のときの動作ですか。

組織が、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の動的な配信を使用して添付ファイルを含む電子メールを受け取る他のユーザーとします。今すぐその人が他のユーザーに電子メール メッセージを転送しようとしていますがいると仮定します。どうなりますか。ATP の安全な添付ファイル ポリシーに追加の受信者が含まれているかどうかによって異なります。
  
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
    
- ホストされているメールボックスとアーカイブのフォルダーを含む、他の場所に (自動または手動で) 移動されたメッセージ
    
- 削除されたメッセージ
    
- エラー状態では、ユーザーのメールボックスの検索フォルダー
    
- Exclaimer Exchange Online 管理者が有効にする環境。( [ATP の動的な配信および Exclaimer を使用すると、添付ファイル付きのメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)を参照してください)
    
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP の安全な添付ファイルを Office 365 で](atp-safe-attachments.md)
  
[Office 365 の ATP の安全な添付ファイル ポリシーを設定します](set-up-atp-safe-attachments-policies.md)
  
[Office 365 で ATP の安全なリンク](atp-safe-links.md)

[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)
  

