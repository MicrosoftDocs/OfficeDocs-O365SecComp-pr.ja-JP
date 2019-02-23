---
title: Office 365 で脅威から保護する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection: M365-security-compliance
description: Office 365 Enterprise が、スプーフィング、マルウェア、スパム、フィッシングの試行、データへの無許可アクセスなどのさまざまな脅威から組織を保護する方法について説明します。
ms.openlocfilehash: ca2bfda0403a1f482989977f7bc018bbd94afeb5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220487"
---
# <a name="protect-against-threats-in-office-365"></a>Office 365 で脅威から保護する

Office 365 Enterprise を使用すると、スプーフィング、マルウェア、スパム、フィッシングの試行、データへの無許可アクセスなどのさまざまな脅威から組織を保護することができます。このページのリソースを使用して、脅威に対する保護と実行できる処置について説明します。
  
## <a name="anti-spoofing"></a>スプーフィング対策

Office 365 でカスタムドメインを使用している場合は、組織からの送信者の詐欺を防止し、電子メールのセキュリティを向上させ、ドメインの評価を保護します。
  
- [スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
- [DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)
    
- [DMARC を使用して Office 365 でメールを検証する](use-dmarc-to-validate-email.md)
    
## <a name="anti-spam-amp-anti-malware"></a>スパム&amp;対策マルウェア対策

Office 365 のスパム対策スコアリング、接続フィルター、およびマルウェアキャプチャについて説明します。これには、既定の設定や悪意のある電子メールを報告する方法が含まれます。
  
- [スパム&amp;対策マルウェア対策保護](anti-spam-and-anti-malware-protection.md)
    
- [Office 365 でメールボックスの監査を有効にする](enable-mailbox-auditing.md)
    
- [Office 365 でメール メッセージを検疫する](quarantine-email-messages.md)
    
- [マルウェアおよびマルウェアでないファイルを分析のために Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
    
## <a name="advanced-threat-protection"></a>Advanced Threat Protection

高度な脅威保護 (ATP) を使用して、スプーフィングを管理し、フィッシング攻撃から保護し、電子メールメッセージ内の悪意のある url やファイルを検出するポリシーを構成します。
  
- [Office 365 ATP について](office-365-atp.md)
    
- [スプーフィングインテリジェンスについて](learn-about-spoof-intelligence.md)
    
- [フィッシング対策ポリシーを設定する](set-up-anti-phishing-policies.md)
    
- [ATP の安全なリンク機能のポリシーを設定する](set-up-atp-safe-links-policies.md)
    
- [ATP の安全な添付ファイル機能のポリシーを設定する](set-up-atp-safe-attachments-policies.md)
    
## <a name="encryption"></a>暗号化

暗号化の入門を行い、rights management ポリシーおよび電子メールの暗号化を設定し、追加の暗号化設定を構成します。Office 365 用のメールサーバーによって使用されるルート証明書の詳細を取得します。
  
- [Office 365 での暗号化について](encryption.md)
    
- [Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
    
- [Office 365 Message Encryption (OME)](ome.md)
    
- [を実装して独自のキーを作成する (byok)](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys#implementing-bring-your-own-key-byok-for-azure-key-vault)
    
## <a name="managing-devices-amp-apps"></a>デバイス&amp;アプリを管理する

モバイルデバイスが Office 365 データにアクセスする方法を監視および制御し、組織で使用されているモバイルアプリの禁止または承認を行います。
  
- [デバイス セキュリティ ポリシーを作成して展開する](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)
    
- [Office 365 Cloud App Security を使用してアプリのアクセス許可を管理する](manage-app-permissions-in-ocas.md)
    
## <a name="threat-intelligence"></a>脅威インテリジェンス

攻撃の識別、監視、および理解を行い、攻撃を防止するために利用可能な洞察と知識を使用して、脅威にすばやく対処します。
  
- [Office 365 脅威インテリジェンスの概要を理解する](office-365-ti.md)
    
- [Office 365 脅威インテリジェンスの概要](get-started-with-ti.md)
    
## <a name="privileged-access-management"></a>特権アクセスの管理

機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある、侵害から組織を保護します。特権アクセス管理を有効にした後、ユーザーは、範囲と時間を制限された承認ワークフローを使用して、昇格された権限のあるタスクを完了するためにジャストインタイムアクセスを要求する必要があります。
  
- [特権アクセス管理の概要を理解する](privileged-access-management-overview.md)
    
- [特権アクセス管理の概要](privileged-access-management-configuration.md)

## <a name="additional-options"></a>その他のオプション

脅威に対して Office 365 をセキュリティで保護するために役立つ、関連する Microsoft のテクノロジとプロセスに関する詳細情報を取得します。
  
- [Azure Rights Management について](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [Azure Key Vault について](https://docs.microsoft.com/azure/key-vault/)
    
- [テナントの分離について](http://download.microsoft.com/download/3/F/0/3F0420A2-657B-44B6-B21E-D7BD98A94390/Tenant%20Isolation%20in%20Office%20365.pdf)
    

