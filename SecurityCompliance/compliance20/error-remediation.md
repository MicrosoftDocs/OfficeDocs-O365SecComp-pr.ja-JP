---
title: データ処理中のエラー修復
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c9c2660929037430535c9b612218563c51b1f056
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490794"
---
# <a name="error-remediation-when-processing-data"></a>データ処理中のエラー修復

エラー修復により、電子情報開示管理者は、コンテンツを適切に処理できなくなるデータの問題を修正することができます。 たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。 エラー修復を使用すると、電子情報開示管理者は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復したファイルをアップロードできます。

次のワークフローを使用して、高度な電子情報開示ケースでエラーが発生したファイルを修復します。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>エラー修復セッションを作成して処理エラーが発生したファイルを修復する

>[!NOTE]
>次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error **** **remediations** ] を選択することにより、エラー修復セッションに戻ることができます。

1. 高度な電子情報開示ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。

2. エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。  次の例では、パスワードで保護されたファイルを修復しています。

3. [**新しいエラーの修復**] をクリックします。

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    エラー修復セッションは、エラーが発生したファイルを Microsoft 提供の Azure ストレージの場所にコピーして、それをローカルコンピューターにダウンロードして修復できるようにする準備段階で開始します。

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。 これは、ファイルがダウンロードされるローカルコンピューター上のパスです。  既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。 このパスは必要に応じて変更できます。 これを変更する場合は、最適なパフォーマンスを得るためにローカルファイルパスを使用することをお勧めします。 リモートネットワークパスは使用しないでください。

6. [**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。  

    ファイルがダウンロードされます。

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > [**ファイルのダウンロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。 また、AzCopy v1.1 を使用して、以下の手順10でファイルをアップロードする必要があります。 このバージョンの AzCopy をインストールするには、「 [Transfer data With AzCopy v2.0 On Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」を参照してください。 指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。

7. ファイルをダウンロードした後、適切なツールを使用して修復できます。 パスワードで保護されたファイルでは、いくつかのパスワードクラッキングツールを使用できます。 ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。
    > [!NOTE]
    > 修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。 ダウンロードしたファイルとフォルダーのパス名によって、修復済みのファイルを元のファイルに関連付けることができます。  ディレクトリ構造またはファイル名が変更されると、次のエラーが表示`Cannot apply Error Remediation to the current Workingset`されます。

8. [Advanced eDiscovery] に戻り、[**次へ: ファイルのアップロード**] をクリックします。  これにより、次の手順に進み、ファイルをアップロードできるようになります。

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. [**ファイルの場所へのパス**] テキストボックスに修復したファイルの場所を指定し、[**クリップボードにコピー] を**クリックします。

10. コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. [Advanced eDiscovery] に戻り、[**次へ: ファイルの処理**] をクリックします。

12. 処理が完了したとき。 レビューセットに戻り、修復されたファイルを確認することができます。

## <a name="what-happens-when-files-are-remediated"></a>ファイルが修復されたときの処理

修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- テキスト
- WordCount
- WorkingsetId

Advanced eDiscovery のすべてのメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。
