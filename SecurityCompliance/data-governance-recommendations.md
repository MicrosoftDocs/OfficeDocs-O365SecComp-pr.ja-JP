---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: a3f803105ea5c2626c8c2a26ad898df5f45af2f0
ms.sourcegitcommit: c7737903ff2e1d047682ee61f7ac21b0bdd1c6fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28263946"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>データ ガバナンスの推奨事項のためのコンテンツの識別方法

Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。

このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。

## <a name="clean-up-voicemail"></a>ボイスメールのクリーンアップ

この推奨事項は、メッセージの種類が “ボイスメール” と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。

## <a name="label-attorney-client-privilege-content"></a>弁護士/依頼人特権関連コンテンツのラベル付け 

この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。

- メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。
    - ACP
    - 弁護士依頼人特権
    - 弁護士/依頼人特権
    - 弁護士/依頼人特権がある

- SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます
    - ACP
    - 弁護士依頼人特権*
    - AC 特権

## <a name="retain-audio-files"></a>オーディオ ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>CAD ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>画像ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>NDA 関連コンテンツの保持 

この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。

- メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。
    - NDA
    - “秘密保持契約”
    - “秘密保持契約”

- SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。
    - NDA
    - “秘密保持契約”

## <a name="retain-software-development-files"></a>ソフトウェア開発ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>ビデオ ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
