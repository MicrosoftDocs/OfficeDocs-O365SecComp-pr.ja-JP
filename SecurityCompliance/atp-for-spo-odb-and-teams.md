---
title: SharePoint、OneDrive、Microsoft Teams 用の Microsoft Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: SharePoint Online で、組織の安全なコラボレーションを有効にするには、ビジネス、およびマイクロソフトのチームの OneDrive 内のファイルには、Office 365 の高度な脅威保護を拡張します。
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532572"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の Microsoft Office 365 ATP

人が定期的にファイルを共有し、SharePoint、OneDrive、およびマイクロソフトのチームを使用して共同作業を行います。[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) のより安全な方法で共同作業を行う組織です。分析ツールは、検出し、チーム サイトおよびドキュメント ライブラリで悪意あるコードとして指定されているファイルをブロックすることができます。SharePoint のオンライン、OneDrive のビジネス、およびマイクロソフトのチームの分析ツールの概要を取得するには、この記事を読むし、次の手順を実行します。 
  
> [!TIP]
> この資料で説明するタスクを実行するために Office 365 のグローバル管理者またはセキュリティ管理者でなければなりません。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="how-it-works"></a>しくみ

SharePoint Online でのファイル、ビジネス、およびマイクロソフトのチームの OneDrive 確認された、悪意のある、分析ツールは、そのファイルをロックするのにはファイル ストアに直接統合されます。次の図は、ライブラリで検出された悪意のあるファイルの例を示します。
  
[![悪意のあるものとして検出された 1 つのビジネスの OneDrive 内のファイルのスクリーン ショット](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
ブロックされたファイルはドキュメント ライブラリと web、モバイル、またはデスクトップのアプリケーションにも示されています。 ブロックされたファイルを開けなかったり、コピー、移動、共有。人、ただし、ファイルを削除ブロックします。ここでどのようなことの一例が、ユーザーのモバイル デバイス上のようになります。
  
[![ビジネスの OneDrive から OneDrive のモバイル アプリケーションからブロックされたファイルを削除するのスクリーン ショット](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Office 365 の構成方法によってユーザーには、ブロックされたファイルをダウンロードする機能がない可能性があります。ブロックされたファイルのダウンロードがどのようにユーザーのモバイル デバイスを以下に示します。
  
[![ビジネスの OneDrive でブロックされたファイルのダウンロードのスクリーン ショット](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
詳細については、 [SharePoint、OneDrive、およびマイクロソフトのチームの Office 365 の分析ツールを有効にする](turn-on-atp-for-spo-odb-and-teams.md)を参照してください。
  
### <a name="keep-the-following-points-in-mind"></a>次の点に留意します。

- 分析ツールでは、ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive では、すべてのファイルはスキャンしません。これは仕様です。スマート ヒューリスティックおよび脅威の信号と共有し、ゲストのアクティビティのイベントを使用して、悪意のあるファイルを特定するプロセスを非同期的にファイルがスキャンされます。
    
- SharePoint Online で悪意のあるものとして指定されているファイルの場合は、ビジネス、またはマイクロソフトのチームの OneDrive が表示されます[Office 365 の高度な脅威保護のためのレポート](view-reports-for-atp.md)と脅威のエクスプ ローラー ( [Office 365 の脅威インテリジェンス](office-365-ti.md)の一部)。
    
- 分析ツールは、組織の全体的な脅威保護戦略、スパム対策とマルウェア対策の保護と安全なリンクと安全な添付ファイルを含む部分です。詳細については、 [Office 365 の脅威から保護する](protect-against-threats.md)を参照してください。
    
- SharePoint Online 管理者は、悪意あるコードとして検出されたファイルをダウンロードするユーザーを有効にするかどうかを判断できます。DisallowInfectedFileDownload パラメーターを使用してセット SPOTenant PowerShell コマンドレットを実行して、これは ( [SharePoint、OneDrive、およびマイクロソフトのチームの Office 365 の分析ツールを有効にする](turn-on-atp-for-spo-odb-and-teams.md)を参照してください)。
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>(New!)オンラインでは、SharePoint の ATP 検査、ビジネス、およびマイクロソフトのチームの OneDrive

 * * 遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能で始まる&amp;コンプライアンス センターが拡張される ATP を SharePoint のオンラインでのビジネス、およびマイクロソフトのチームの OneDrive。 **
  
SharePoint Online でのファイル、ビジネス、またはマイクロソフトのチームの OneDrive は ATP を開けない状態、または共有からファイルをブロックするだけでなく、悪意のある、検疫済みのアイテムの一覧でそのファイルが含まれています。(セキュリティ&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**レビュー** \> **検査**し、コンテンツのフィルターします)。 
  
組織の Office 365 のセキュリティ チームの一部になっている必要がある場合[Office 365 のセキュリティに割り当てられたアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)、ダウンロード、リリース、レポート、および分析ツールで悪意あるコードとして検出されたファイルを削除隔離します。
  
- **解放してレポート**ファイルは、SharePoint、OneDrive、またはマイクロソフトのチームのそれぞれのチーム サイトまたはドキュメント ライブラリで、ATP のブロック、ファイルを削除します。開き、共有、およびファイルをダウンロードすることもできます。**マイクロソフトにレポートを送信**する] オプションを選択すると、ファイルがマイクロソフトに報告として誤検知します。 
    
- 検疫; からファイルを削除する**ファイルを削除します。** ただし、ファイルはまだされるを禁止を開く、または共有します。ファイルは、それぞれのドキュメント ライブラリ、またはチーム サイト (SharePoint のオンライン ・ ビジネス、またはマイクロソフトのチームの OneDrive) でも削除しなければなりません。 
    
- **ファイルのダウンロード**を使用すると、ダウンロードし、任意の偽陽性のファイルを分析します。 
    
## <a name="next-steps"></a>次の手順

- [SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に](turn-on-atp-for-spo-odb-and-teams.md)
    
- [SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 の高度な脅威保護のレポートを表示します。](view-reports-for-atp.md)
  
[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)
  

