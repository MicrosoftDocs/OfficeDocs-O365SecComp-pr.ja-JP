---
title: Outlook デスクトップ用の監督アドインをインストールする
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Outlook のデスクトップのバージョンの Office 365 の監視アドインのインストールします。
ms.openlocfilehash: 0bddf305087bf0d9552c7671da5306db8352143f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531661"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a>Outlook デスクトップ用の監督アドインをインストールする

監督ポリシーによって特定の通信を確認するには、監督を追加で、Outlook および Outlook の校閲者の使用の web アプリケーション。アドインが自動的にインストール Outlook web app で、ポリシーで指定したすべての校閲者の。ただし、レビュー担当者は、デスクトップのバージョンの Outlook をインストールするのにはいくつかの手順を実行しなければなりません。
  
> [!NOTE]
> 監督ポリシーを使用して、組織に、Office 365 の E5 のサブスクリプションが必要です。しない計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>監督のメールボックスのアドレスをコピーする手順 1。

Outlook デスクトップ用のアドインをインストールするには、監督のポリシー設定の一部として作成された監督のメールボックスのアドレスを必要があります。 
  
> [!NOTE]
> だれかそれ以外の場合、ポリシーを作成する場合は、アドインをインストールするのにはこれらのファイルからこのアドレスを取得する必要があります。 
  
 **監督のメールボックスのアドレスを検索するには**
  
1. サインイン、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。 
    
2. **データ ・ ガバナンス**に\>**監督**します。
    
3. 監督ポリシーを確認する通信を収集する] をクリックします。
    
4. ポリシーの詳細] の [フライアウトを表示 * * 監督メールボックス * *、アドレスをコピーします。 
    
    ![監督ポリシーの詳細のフライアウトが強調表示されている監督のメールボックスのアドレスが表示されているの「メールボックスの監視」セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>ステップ 2: Outlook デスクトップからのアクセスの監視のメールボックスを構成します。

次に、校閲者は、監督のメールボックスを Outlook に接続するためにはいくつかの Exchange のオンラインの PowerShell コマンドを実行する必要があります。
  
1. オンライン PowerShell を交換するために接続します。[これはどのようにしますか?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
    
2. 次のコマンドを実行します。
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    *SupervisoryReview{GUID}@domain.onmicrosoft.com*では、上記の手順 1 でコピーしたアドレスと、*ユーザー*は、次の手順で監督のメールボックスに接続する人の校閲者の名前。 
    
3. 以下の手順 3 移動する前に 1 時間以上まで待機します。
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>監督のメールボックスに接続する Outlook プロファイルを作成する手順 3。

最後の手順では、校閲者は、監督のメールボックスに接続する Outlook プロファイルを作成する必要があります。 
  
> [!NOTE]
> 新しい Outlook プロファイルを作成するには、Windows コントロール パネルの [メールの設定を使用します。これらの設定を取得するためのパスは、Windows オペレーティング システム (Windows 7、Windows 8 の場合、または Windows の 10) を使用している Outlook のバージョンがインストールされているによって異なります。 
  
1. [コントロール パネル] を開き、ウィンドウの上部にある [**検索**] ボックスで**メール**を入力します。 
    
    > [!NOTE]
    > いないことを確認してコントロール パネルを取得する方法ですか。参照してください[場所は、コントロール パネルの [?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. **メール**アプリケーションを開きます。 
    
3. **メール設定 - Outlook****プロファイルの表示**をクリックします。
    
    ![' メール設定 - Outlook] ダイアログ ボックスに、プロファイルの表示] ボタンがハイライトされます](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. [**メール**] の [**追加**を] をクリックします。**新しいプロファイル**(**監督**) などの監督のメールボックスの名前を入力します。
    
    !['監督' の名前を示す、[プロファイル名] ボックスで [新しいプロファイル] ダイアログ ボックス](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. **Outlook に接続**、**別のアカウントへの接続**をクリックします。
    
    ![強調表示されている別のアカウントへ接続] リンクを使用して Office 365 に Outlook を接続する ' メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. **自動アカウント セットアップ**では、**手動設定] または [その他のサーバー**を選択し、[**次へ**] をクリックします。
    
7. **アカウント タイプの選択**] では、 **Office 365**を選択します。**電子メール アドレス**] ボックスで、以前にコピーした監督のメールボックスのアドレスを入力します。 
    
    ![強調表示されている [電子メール アドレス] ボックスを表示する Outlook の [アカウントの追加] ダイアログ ボックスの ' のアカウントの種類の選択] ページです。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. ダイアログ ボックスが表示されたら、Office 365 のユーザーの資格情報を入力します。
    
9. 成功すると、表示されます、**監督 -\<ポリシー名\>** フォルダーが Outlook のフォルダー一覧ビューで表示します。 
    

