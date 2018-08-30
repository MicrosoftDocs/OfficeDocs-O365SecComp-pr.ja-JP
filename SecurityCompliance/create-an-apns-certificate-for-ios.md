---
title: IOS デバイス用の Apn 証明書を作成します。
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Office 365 の iPad とモバイル デバイス管理の iPhones のように iOS のデバイスを管理するために最初に Apn の証明書を作成するのにはこれら手順を実行します。
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272052"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>IOS デバイス用の Apn 証明書を作成します。

 Office 365 の iPad とモバイル デバイス管理の iPhones のように iOS のデバイスを管理するには、Apn の証明書を作成してください。 
  
これを行うには、ポータル ページ**設定**リンクの手順に従います。(には、**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイス管理** \> **の設定の管理**)。
  
![モバイル デバイスの管理に必要な推奨手順を設定します](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. **IOS デバイス用の Apn 証明書を構成する**] の横にある**設定**を選択します。
    
2. **CSR ファイルをダウンロード**] を選択し、任意の場所に証明書署名要求を保存する、わかりやすいコンピューターにします。 
    
    ![APN の証明書] ダイアログ ボックスをインストールします。](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. **次へ**を選択します。
    
4. APN の証明書を作成します。
    
  - 開くには、Apple のプッシュ証明書ポータル**アップル APN のポータル**を選択します。 
    
    ![選択 Apple APN ポータルでの APN 通知証明書] ダイアログをインストールします。](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Apple ID でサインイン
    
    > [!IMPORTANT]
    > Apple ID は、アカウントを管理しているユーザーを離れた場合でも、組織に残る電子メール アカウントに関連付けられている会社を使用します。証明書を更新する時と同じ ID を使用する必要がありますので、この ID を保存します。 
  
  - **証明書の作成**を選択し、**使用条件**に同意します。
    
  - 証明書署名要求**をアップロード**を選択し、Office 365 からコンピューターにダウンロードするには、**参照**をします。
    
  - **ダウンロード**APN の証明書は、お使いのコンピューターに Apple プッシュ証明書ポータルによって作成されます。 
    
    > [!TIP]
    > 、証明書のダウンロードで問題が発生した場合は、ブラウザーを更新します。 
  
5. Office 365 に戻るし、**次****アップロード APN の証明書**のページを表示するを選択します。 
    
6. アップル プッシュ証明書ポータルからダウンロードした APN の証明書を参照します。
    
    ![アップルからダウンロードした APN の証明書を選択するのには [参照] ボタンをクリックします。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. **終了**を選択します。
    
戻る**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイス管理** \> **設定の管理**セットアップを完了します。 
  

