---
title: Office 365 の証明書チェーン
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャのインストール、Office 365 のサード パーティの SSL 証明書の計画を参照してくださいする必要があります。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。
ms.openlocfilehash: 97e00833e57f8f6b7352650b0efdef51ddba77fa
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575361"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="a37db-106">Office 365 の証明書チェーン</span><span class="sxs-lookup"><span data-stu-id="a37db-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="a37db-p102">Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャをインストールする必要があります、 [Office 365 の SSL 証明書をサード ・ パーティの計画](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)を参照してください。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a37db-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="a37db-111">**証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="a37db-111">**Certificate type**</span></span>|<span data-ttu-id="a37db-112">**P7b ダウンロード**</span><span class="sxs-lookup"><span data-stu-id="a37db-112">**P7b download**</span></span>|<span data-ttu-id="a37db-113">**CRL の端点**</span><span class="sxs-lookup"><span data-stu-id="a37db-113">**CRL Endpoints**</span></span>|<span data-ttu-id="a37db-114">**OCSP の端点**</span><span class="sxs-lookup"><span data-stu-id="a37db-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="a37db-115">**AIA の端点**</span><span class="sxs-lookup"><span data-stu-id="a37db-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="a37db-116">信頼関係のルート証明書の公開</span><span class="sxs-lookup"><span data-stu-id="a37db-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="a37db-117">Office 365 のルート証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="a37db-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="a37db-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="a37db-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a37db-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a37db-120">該当なし</span><span class="sxs-lookup"><span data-stu-id="a37db-120">N/A</span></span>  <br/> |<span data-ttu-id="a37db-121">該当なし</span><span class="sxs-lookup"><span data-stu-id="a37db-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="a37db-122">一般に中間証明書を信頼</span><span class="sxs-lookup"><span data-stu-id="a37db-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="a37db-123">Office 365 の中間証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="a37db-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="a37db-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="a37db-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="a37db-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a37db-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="a37db-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="a37db-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a37db-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="a37db-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="a37db-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a37db-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a37db-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="a37db-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="a37db-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="a37db-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a37db-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="a37db-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a37db-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="a37db-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a37db-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="a37db-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a37db-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a37db-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="a37db-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a37db-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="a37db-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="a37db-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a37db-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="a37db-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="a37db-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="a37db-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a37db-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="a37db-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="a37db-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="a37db-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a37db-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="a37db-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a37db-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="a37db-144">ルート-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a37db-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a37db-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a37db-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a37db-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="a37db-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a37db-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="a37db-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a37db-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="a37db-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="a37db-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="a37db-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a37db-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="a37db-151">ルートと証明書プロバイダーに関する追加情報を参照してください次の中間のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a37db-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="a37db-152">Office 365 のルート証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="a37db-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="a37db-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a37db-153"></span></span>

 <span data-ttu-id="a37db-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="a37db-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="a37db-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="a37db-155">|:-----|</span></span>
|<span data-ttu-id="a37db-156">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="a37db-157">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-157">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-158">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-158"></span></span>|
|<span data-ttu-id="a37db-159">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-159">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-160">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-160"></span></span>|
|<span data-ttu-id="a37db-161">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-162">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-162"></span></span>|
|<span data-ttu-id="a37db-163">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-164">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-164"></span></span>|
|<span data-ttu-id="a37db-165">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-165">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-166">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-166"></span></span>|
|<span data-ttu-id="a37db-167">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-168">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-168"></span></span>|
|<span data-ttu-id="a37db-169">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-170">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-170"></span></span>|
|<span data-ttu-id="a37db-171">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-172">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-172"></span></span>|
|<span data-ttu-id="a37db-173">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-174">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-174"></span></span>|
   
 <span data-ttu-id="a37db-175">**CNNIC のルート**</span><span class="sxs-lookup"><span data-stu-id="a37db-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-176">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-176">**Subject**</span></span>|
|<span data-ttu-id="a37db-177">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-177"></span></span>|
|<span data-ttu-id="a37db-178">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-178">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-179">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-179"></span></span>|
|<span data-ttu-id="a37db-180">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-180">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-181">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-181"></span></span>|
|<span data-ttu-id="a37db-182">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-183">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-183"></span></span>|
|<span data-ttu-id="a37db-184">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-185">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-185"></span></span>|
|<span data-ttu-id="a37db-186">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-186">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-187">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-187"></span></span>|
|<span data-ttu-id="a37db-188">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-189">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-189"></span></span>|
|<span data-ttu-id="a37db-190">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-191">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-191"></span></span>|
|<span data-ttu-id="a37db-192">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-193">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-193"></span></span>|
|<span data-ttu-id="a37db-194">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-195">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-195"></span></span>|
|<span data-ttu-id="a37db-196">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-197">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-197"></span></span>|
   
 <span data-ttu-id="a37db-198">**DigiCert のグローバル ルート CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-199">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-199">**Subject**</span></span>|
|<span data-ttu-id="a37db-200">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-200"></span></span>|
|<span data-ttu-id="a37db-201">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-201">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-202">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-202"></span></span>|
|<span data-ttu-id="a37db-203">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-203">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-204">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-204"></span></span>|
|<span data-ttu-id="a37db-205">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-206">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-206"></span></span>|
|<span data-ttu-id="a37db-207">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-208">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-208"></span></span>|
|<span data-ttu-id="a37db-209">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-209">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-210">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-210"></span></span>|
|<span data-ttu-id="a37db-211">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-212">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-212"></span></span>|
|<span data-ttu-id="a37db-213">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-214">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-214"></span></span>|
|<span data-ttu-id="a37db-215">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-216">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-216"></span></span>|
|<span data-ttu-id="a37db-217">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-218">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-218"></span></span>|
|<span data-ttu-id="a37db-219">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-220">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-220"></span></span>|
   
 <span data-ttu-id="a37db-221">**DigiCert 高保証 EV のルート CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-222">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-222">**Subject**</span></span>|
|<span data-ttu-id="a37db-223">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-223"></span></span>|
|<span data-ttu-id="a37db-224">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-224">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-225">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-225"></span></span>|
|<span data-ttu-id="a37db-226">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-226">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-227">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-227"></span></span>|
|<span data-ttu-id="a37db-228">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-229">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-229"></span></span>|
|<span data-ttu-id="a37db-230">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-231">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-231"></span></span>|
|<span data-ttu-id="a37db-232">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-232">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-233">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-233"></span></span>|
|<span data-ttu-id="a37db-234">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-235">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-235"></span></span>|
|<span data-ttu-id="a37db-236">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-237">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-237"></span></span>|
|<span data-ttu-id="a37db-238">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-239">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-239"></span></span>|
|<span data-ttu-id="a37db-240">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-241">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-241"></span></span>|
|<span data-ttu-id="a37db-242">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-243">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-243"></span></span>|
   
 <span data-ttu-id="a37db-244">**D 信頼ルート クラス 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="a37db-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-245">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-245">**Subject**</span></span>|
|<span data-ttu-id="a37db-246">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-246"></span></span>|
|<span data-ttu-id="a37db-247">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-247">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-248">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-248"></span></span>|
|<span data-ttu-id="a37db-249">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-249">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-250">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-250"></span></span>|
|<span data-ttu-id="a37db-251">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-252">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-252"></span></span>|
|<span data-ttu-id="a37db-253">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-254">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-254"></span></span>|
|<span data-ttu-id="a37db-255">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-255">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-256">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-256"></span></span>|
|<span data-ttu-id="a37db-257">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-258">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-258"></span></span>|
|<span data-ttu-id="a37db-259">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-260">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-260"></span></span>|
|<span data-ttu-id="a37db-261">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-262">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-262"></span></span>|
|<span data-ttu-id="a37db-263">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-264">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-264"></span></span>|
|<span data-ttu-id="a37db-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-265">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-266">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-266"></span></span>|
   
 <span data-ttu-id="a37db-267">**クラス 3 の D に信頼できるルート CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="a37db-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-268">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-268">**Subject**</span></span>|
|<span data-ttu-id="a37db-269">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-269"></span></span>|
|<span data-ttu-id="a37db-270">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-270">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-271">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-271"></span></span>|
|<span data-ttu-id="a37db-272">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-272">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-273">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-273"></span></span>|
|<span data-ttu-id="a37db-274">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-275">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-275"></span></span>|
|<span data-ttu-id="a37db-276">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-277">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-277"></span></span>|
|<span data-ttu-id="a37db-278">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-278">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-279">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-279"></span></span>|
|<span data-ttu-id="a37db-280">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-281">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-281"></span></span>|
|<span data-ttu-id="a37db-282">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-283">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-283"></span></span>|
|<span data-ttu-id="a37db-284">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-285">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-285"></span></span>|
|<span data-ttu-id="a37db-286">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-287">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-287"></span></span>|
|<span data-ttu-id="a37db-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-288">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-289">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-289"></span></span>|
   
 <span data-ttu-id="a37db-290">**DST のルート CA X3**</span><span class="sxs-lookup"><span data-stu-id="a37db-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-291">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-291">**Subject**</span></span>|
|<span data-ttu-id="a37db-292">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-292"></span></span>|
|<span data-ttu-id="a37db-293">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-293">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-294">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-294"></span></span>|
|<span data-ttu-id="a37db-295">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-295">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-296">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-296"></span></span>|
|<span data-ttu-id="a37db-297">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-298">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-298"></span></span>|
|<span data-ttu-id="a37db-299">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-300">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-300"></span></span>|
|<span data-ttu-id="a37db-301">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-301">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-302">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-302"></span></span>|
|<span data-ttu-id="a37db-303">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-304">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-304"></span></span>|
|<span data-ttu-id="a37db-305">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-306">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-306"></span></span>|
|<span data-ttu-id="a37db-307">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-308">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-308"></span></span>|
|<span data-ttu-id="a37db-309">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-310">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-310"></span></span>|
   
 <span data-ttu-id="a37db-311">**ルート証明機関の G2 を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a37db-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-312">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-312">**Subject**</span></span>|
|<span data-ttu-id="a37db-313">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-313"></span></span>|
|<span data-ttu-id="a37db-314">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-314">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-315">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-315"></span></span>|
|<span data-ttu-id="a37db-316">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-316">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-317">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-317"></span></span>|
|<span data-ttu-id="a37db-318">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-319">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-319"></span></span>|
|<span data-ttu-id="a37db-320">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-321">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-321"></span></span>|
|<span data-ttu-id="a37db-322">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-322">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-323">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-323"></span></span>|
|<span data-ttu-id="a37db-324">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-325">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-325"></span></span>|
|<span data-ttu-id="a37db-326">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-327">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-327"></span></span>|
|<span data-ttu-id="a37db-328">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-329">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-329"></span></span>|
|<span data-ttu-id="a37db-330">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-331">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-331"></span></span>|
   
 <span data-ttu-id="a37db-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="a37db-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-333">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-333">**Subject**</span></span>|
|<span data-ttu-id="a37db-334">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-334"></span></span>|
|<span data-ttu-id="a37db-335">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-335">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-336">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-336"></span></span>|
|<span data-ttu-id="a37db-337">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-337">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-338">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-338"></span></span>|
|<span data-ttu-id="a37db-339">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-340">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-340"></span></span>|
|<span data-ttu-id="a37db-341">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-342">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-342"></span></span>|
|<span data-ttu-id="a37db-343">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-343">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-344">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-344"></span></span>|
|<span data-ttu-id="a37db-345">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-346">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-346"></span></span>|
|<span data-ttu-id="a37db-347">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-348">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-348"></span></span>|
|<span data-ttu-id="a37db-349">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-350">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-350"></span></span>|
|<span data-ttu-id="a37db-351">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-352">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-352"></span></span>|
   
 <span data-ttu-id="a37db-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a37db-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-354">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-354">**Subject**</span></span>|
|<span data-ttu-id="a37db-355">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-355"></span></span>|
|<span data-ttu-id="a37db-356">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-356">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-357">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-357"></span></span>|
|<span data-ttu-id="a37db-358">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-358">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-359">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-359"></span></span>|
|<span data-ttu-id="a37db-360">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-361">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-361"></span></span>|
|<span data-ttu-id="a37db-362">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-363">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-363"></span></span>|
|<span data-ttu-id="a37db-364">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-364">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-365">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-365"></span></span>|
|<span data-ttu-id="a37db-366">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-367">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-367"></span></span>|
|<span data-ttu-id="a37db-368">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-369">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-369"></span></span>|
|<span data-ttu-id="a37db-370">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-371">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-371"></span></span>|
|<span data-ttu-id="a37db-372">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-373">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-373"></span></span>|
|<span data-ttu-id="a37db-374">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-375">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-375"></span></span>|
|<span data-ttu-id="a37db-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-376">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-377">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-377"></span></span>|
   
 <span data-ttu-id="a37db-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-379">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-379">**Subject**</span></span>|
|<span data-ttu-id="a37db-380">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-380"></span></span>|
|<span data-ttu-id="a37db-381">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-381">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-382">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-382"></span></span>|
|<span data-ttu-id="a37db-383">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-383">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-384">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-384"></span></span>|
|<span data-ttu-id="a37db-385">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-386">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-386"></span></span>|
|<span data-ttu-id="a37db-387">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-388">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-388"></span></span>|
|<span data-ttu-id="a37db-389">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-389">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-390">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-390"></span></span>|
|<span data-ttu-id="a37db-391">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-392">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-392"></span></span>|
|<span data-ttu-id="a37db-393">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-394">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-394"></span></span>|
|<span data-ttu-id="a37db-395">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-396">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-396"></span></span>|
|<span data-ttu-id="a37db-397">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-398">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-398"></span></span>|
   
 <span data-ttu-id="a37db-399">**thawte プライマリ ルート CA の場合は、G3**</span><span class="sxs-lookup"><span data-stu-id="a37db-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-400">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-400">**Subject**</span></span>|
|<span data-ttu-id="a37db-401">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-401"></span></span>|
|<span data-ttu-id="a37db-402">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-402">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-403">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-403"></span></span>|
|<span data-ttu-id="a37db-404">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-404">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-405">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-405"></span></span>|
|<span data-ttu-id="a37db-406">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-407">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-407"></span></span>|
|<span data-ttu-id="a37db-408">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-409">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-409"></span></span>|
|<span data-ttu-id="a37db-410">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-410">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-411">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-411"></span></span>|
|<span data-ttu-id="a37db-412">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-413">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-413"></span></span>|
|<span data-ttu-id="a37db-414">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-415">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-415"></span></span>|
|<span data-ttu-id="a37db-416">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-417">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-417"></span></span>|
|<span data-ttu-id="a37db-418">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-419">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-419"></span></span>|
   
 <span data-ttu-id="a37db-420">**VeriSign クラス 3 の主な公共の証明機関の G5**</span><span class="sxs-lookup"><span data-stu-id="a37db-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-421">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-421">**Subject**</span></span>|
|<span data-ttu-id="a37db-422">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-422"></span></span>|
|<span data-ttu-id="a37db-423">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-423">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-424">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-424"></span></span>|
|<span data-ttu-id="a37db-425">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-425">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-426">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-426"></span></span>|
|<span data-ttu-id="a37db-427">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-428">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-428"></span></span>|
|<span data-ttu-id="a37db-429">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-430">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-430"></span></span>|
|<span data-ttu-id="a37db-431">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-431">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-432">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-432"></span></span>|
|<span data-ttu-id="a37db-433">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-434">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-434"></span></span>|
|<span data-ttu-id="a37db-435">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-436">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-436"></span></span>|
|<span data-ttu-id="a37db-437">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-438">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-438"></span></span>|
|<span data-ttu-id="a37db-439">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-440">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="a37db-441">Office 365 の中間の証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="a37db-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="a37db-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a37db-442"></span></span>

 <span data-ttu-id="a37db-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="a37db-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-444">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-444">**Subject**</span></span>|
|<span data-ttu-id="a37db-445">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-445"></span></span>|
|<span data-ttu-id="a37db-446">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-446">**Issuer**</span></span>|
|<span data-ttu-id="a37db-447">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-447"></span></span>|
|<span data-ttu-id="a37db-448">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-448">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-449">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-449"></span></span>|
|<span data-ttu-id="a37db-450">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-450">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-451">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-451"></span></span>|
|<span data-ttu-id="a37db-452">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-453">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-453"></span></span>|
|<span data-ttu-id="a37db-454">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-455">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-455"></span></span>|
|<span data-ttu-id="a37db-456">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-456">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-457">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-457"></span></span>|
|<span data-ttu-id="a37db-458">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-459">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-459"></span></span>|
|<span data-ttu-id="a37db-460">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-461">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-461"></span></span>|
|<span data-ttu-id="a37db-462">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-463">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-463"></span></span>|
|<span data-ttu-id="a37db-464">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-465">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-465"></span></span>|
|<span data-ttu-id="a37db-466">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-467">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-467"></span></span>|
|<span data-ttu-id="a37db-468">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-468">**AIA URLs**</span></span>|
|<span data-ttu-id="a37db-469">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-469"></span></span>|
|<span data-ttu-id="a37db-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-470">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-471">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-471"></span></span>|
|<span data-ttu-id="a37db-472">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-473">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-473"></span></span>|
   
 <span data-ttu-id="a37db-474">**D 信頼 SSL クラス 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="a37db-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-475">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-475">**Subject**</span></span>|
|<span data-ttu-id="a37db-476">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-476"></span></span>|
|<span data-ttu-id="a37db-477">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-477">**Issuer**</span></span>|
|<span data-ttu-id="a37db-478">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-478"></span></span>|
|<span data-ttu-id="a37db-479">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a37db-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a37db-480">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-480"></span></span>|
|<span data-ttu-id="a37db-481">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-481">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-482">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-482"></span></span>|
|<span data-ttu-id="a37db-483">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-483">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-484">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-484"></span></span>|
|<span data-ttu-id="a37db-485">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-486">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-486"></span></span>|
|<span data-ttu-id="a37db-487">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-488">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-488"></span></span>|
|<span data-ttu-id="a37db-489">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-489">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-490">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-490"></span></span>|
|<span data-ttu-id="a37db-491">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-492">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-492"></span></span>|
|<span data-ttu-id="a37db-493">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-494">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-494"></span></span>|
|<span data-ttu-id="a37db-495">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-496">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-496"></span></span>|
|<span data-ttu-id="a37db-497">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-498">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-498"></span></span>|
|<span data-ttu-id="a37db-499">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-500">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-500"></span></span>|
|<span data-ttu-id="a37db-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-501">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-502">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-502"></span></span>|
|<span data-ttu-id="a37db-503">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-504">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-504"></span></span>|
   
 <span data-ttu-id="a37db-505">**D 信頼 SSL クラス 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="a37db-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-506">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-506">**Subject**</span></span>|
|<span data-ttu-id="a37db-507">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-507"></span></span>|
|<span data-ttu-id="a37db-508">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-508">**Issuer**</span></span>|
|<span data-ttu-id="a37db-509">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-509"></span></span>|
|<span data-ttu-id="a37db-510">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a37db-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a37db-511">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-511"></span></span>|
|<span data-ttu-id="a37db-512">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-512">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-513">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-513"></span></span>|
|<span data-ttu-id="a37db-514">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-514">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-515">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-515"></span></span>|
|<span data-ttu-id="a37db-516">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-517">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-517"></span></span>|
|<span data-ttu-id="a37db-518">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-519">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-519"></span></span>|
|<span data-ttu-id="a37db-520">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-520">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-521">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-521"></span></span>|
|<span data-ttu-id="a37db-522">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-523">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-523"></span></span>|
|<span data-ttu-id="a37db-524">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-525">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-525"></span></span>|
|<span data-ttu-id="a37db-526">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-527">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-527"></span></span>|
|<span data-ttu-id="a37db-528">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-529">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-529"></span></span>|
|<span data-ttu-id="a37db-530">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-531">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-531"></span></span>|
|<span data-ttu-id="a37db-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-532">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-533">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-533"></span></span>|
|<span data-ttu-id="a37db-534">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-535">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-535"></span></span>|
   
 <span data-ttu-id="a37db-536">**DigiCert のクラウド サービスの CA 1**</span><span class="sxs-lookup"><span data-stu-id="a37db-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-537">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-537">**Subject**</span></span>|
|<span data-ttu-id="a37db-538">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-538"></span></span>|
|<span data-ttu-id="a37db-539">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-539">**Issuer**</span></span>|
|<span data-ttu-id="a37db-540">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-540"></span></span>|
|<span data-ttu-id="a37db-541">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-541">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-542">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-542"></span></span>|
|<span data-ttu-id="a37db-543">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-543">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-544">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-544"></span></span>|
|<span data-ttu-id="a37db-545">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-546">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-546"></span></span>|
|<span data-ttu-id="a37db-547">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-548">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-548"></span></span>|
|<span data-ttu-id="a37db-549">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-549">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-550">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-550"></span></span>|
|<span data-ttu-id="a37db-551">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-552">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-552"></span></span>|
|<span data-ttu-id="a37db-553">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-554">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-554"></span></span>|
|<span data-ttu-id="a37db-555">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-556">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-556"></span></span>|
|<span data-ttu-id="a37db-557">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-558">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-558"></span></span>|
|<span data-ttu-id="a37db-559">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-560">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-560"></span></span>|
|<span data-ttu-id="a37db-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-561">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-562">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-562"></span></span>|
|<span data-ttu-id="a37db-563">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-564">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-564"></span></span>|
   
 <span data-ttu-id="a37db-565">**DigiCert SHA2 高保証サーバー CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-566">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-566">**Subject**</span></span>|
|<span data-ttu-id="a37db-567">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-567"></span></span>|
|<span data-ttu-id="a37db-568">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-568">**Issuer**</span></span>|
|<span data-ttu-id="a37db-569">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-569"></span></span>|
|<span data-ttu-id="a37db-570">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-570">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-571">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-571"></span></span>|
|<span data-ttu-id="a37db-572">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-572">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-573">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-573"></span></span>|
|<span data-ttu-id="a37db-574">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-575">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-575"></span></span>|
|<span data-ttu-id="a37db-576">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-577">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-577"></span></span>|
|<span data-ttu-id="a37db-578">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-578">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-579">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-579"></span></span>|
|<span data-ttu-id="a37db-580">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-581">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-581"></span></span>|
|<span data-ttu-id="a37db-582">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-583">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-583"></span></span>|
|<span data-ttu-id="a37db-584">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-585">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-585"></span></span>|
|<span data-ttu-id="a37db-586">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-587">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-587"></span></span>|
|<span data-ttu-id="a37db-588">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-589">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-589"></span></span>|
|<span data-ttu-id="a37db-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-590">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-591">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-591"></span></span>|
|<span data-ttu-id="a37db-592">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-593">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-593"></span></span>|
   
 <span data-ttu-id="a37db-594">**DigiCert SHA2 セキュリティで保護されたサーバーの CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-595">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-595">**Subject**</span></span>|
|<span data-ttu-id="a37db-596">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-596"></span></span>|
|<span data-ttu-id="a37db-597">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-597">**Issuer**</span></span>|
|<span data-ttu-id="a37db-598">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-598"></span></span>|
|<span data-ttu-id="a37db-599">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-599">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-600">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-600"></span></span>|
|<span data-ttu-id="a37db-601">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-601">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-602">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-602"></span></span>|
|<span data-ttu-id="a37db-603">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-604">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-604"></span></span>|
|<span data-ttu-id="a37db-605">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-606">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-606"></span></span>|
|<span data-ttu-id="a37db-607">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-607">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-608">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-608"></span></span>|
|<span data-ttu-id="a37db-609">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-610">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-610"></span></span>|
|<span data-ttu-id="a37db-611">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-612">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-612"></span></span>|
|<span data-ttu-id="a37db-613">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-614">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-614"></span></span>|
|<span data-ttu-id="a37db-615">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-616">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-616"></span></span>|
|<span data-ttu-id="a37db-617">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-618">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-618"></span></span>|
|<span data-ttu-id="a37db-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-619">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-620">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-620"></span></span>|
|<span data-ttu-id="a37db-621">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-622">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-622"></span></span>|
   
 <span data-ttu-id="a37db-623">**証明機関 - L1C を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a37db-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-624">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-624">**Subject**</span></span>|
|<span data-ttu-id="a37db-625">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-625"></span></span>|
|<span data-ttu-id="a37db-626">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-626">**Issuer**</span></span>|
|<span data-ttu-id="a37db-627">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-627"></span></span>|
|<span data-ttu-id="a37db-628">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-628">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-629">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-629"></span></span>|
|<span data-ttu-id="a37db-630">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-630">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-631">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-631"></span></span>|
|<span data-ttu-id="a37db-632">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-633">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-633"></span></span>|
|<span data-ttu-id="a37db-634">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-635">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-635"></span></span>|
|<span data-ttu-id="a37db-636">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-636">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-637">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-637"></span></span>|
|<span data-ttu-id="a37db-638">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-639">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-639"></span></span>|
|<span data-ttu-id="a37db-640">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-641">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-641"></span></span>|
|<span data-ttu-id="a37db-642">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-643">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-643"></span></span>|
|<span data-ttu-id="a37db-644">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-645">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-645"></span></span>|
|<span data-ttu-id="a37db-646">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-647">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-647"></span></span>|
|<span data-ttu-id="a37db-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-648">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-649">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-649"></span></span>|
|<span data-ttu-id="a37db-650">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-651">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-651"></span></span>|
   
 <span data-ttu-id="a37db-652">**証明機関 - L1K を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a37db-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-653">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-653">**Subject**</span></span>|
|<span data-ttu-id="a37db-654">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-654"></span></span>|
|<span data-ttu-id="a37db-655">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-655">**Issuer**</span></span>|
|<span data-ttu-id="a37db-656">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-656"></span></span>|
|<span data-ttu-id="a37db-657">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-657">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-658">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-658"></span></span>|
|<span data-ttu-id="a37db-659">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-659">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-660">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-660"></span></span>|
|<span data-ttu-id="a37db-661">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-662">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-662"></span></span>|
|<span data-ttu-id="a37db-663">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-664">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-664"></span></span>|
|<span data-ttu-id="a37db-665">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-665">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-666">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-666"></span></span>|
|<span data-ttu-id="a37db-667">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-668">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-668"></span></span>|
|<span data-ttu-id="a37db-669">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-670">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-670"></span></span>|
|<span data-ttu-id="a37db-671">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-672">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-672"></span></span>|
|<span data-ttu-id="a37db-673">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-674">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-674"></span></span>|
|<span data-ttu-id="a37db-675">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-676">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-676"></span></span>|
|<span data-ttu-id="a37db-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-677">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-678">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-678"></span></span>|
|<span data-ttu-id="a37db-679">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-680">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-680"></span></span>|
   
 <span data-ttu-id="a37db-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a37db-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-682">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-682">**Subject**</span></span>|
|<span data-ttu-id="a37db-683">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-683"></span></span>|
|<span data-ttu-id="a37db-684">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-684">**Issuer**</span></span>|
|<span data-ttu-id="a37db-685">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-685"></span></span>|
|<span data-ttu-id="a37db-686">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-686">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-687">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-687"></span></span>|
|<span data-ttu-id="a37db-688">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-688">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-689">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-689"></span></span>|
|<span data-ttu-id="a37db-690">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-691">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-691"></span></span>|
|<span data-ttu-id="a37db-692">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-693">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-693"></span></span>|
|<span data-ttu-id="a37db-694">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-694">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-695">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-695"></span></span>|
|<span data-ttu-id="a37db-696">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-697">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-697"></span></span>|
|<span data-ttu-id="a37db-698">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-699">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-699"></span></span>|
|<span data-ttu-id="a37db-700">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-701">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-701"></span></span>|
|<span data-ttu-id="a37db-702">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-703">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-703"></span></span>|
|<span data-ttu-id="a37db-704">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-705">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-705"></span></span>|
|<span data-ttu-id="a37db-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-706">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-707">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-707"></span></span>|
|<span data-ttu-id="a37db-708">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-709">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-709"></span></span>|
   
 <span data-ttu-id="a37db-710">**GlobalSign の CA の SHA256 の G2 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="a37db-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-711">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-711">**Subject**</span></span>|
|<span data-ttu-id="a37db-712">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-712"></span></span>|
|<span data-ttu-id="a37db-713">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-713">**Issuer**</span></span>|
|<span data-ttu-id="a37db-714">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-714"></span></span>|
|<span data-ttu-id="a37db-715">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-715">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-716">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-716"></span></span>|
|<span data-ttu-id="a37db-717">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-717">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-718">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-718"></span></span>|
|<span data-ttu-id="a37db-719">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-720">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-720"></span></span>|
|<span data-ttu-id="a37db-721">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-722">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-722"></span></span>|
|<span data-ttu-id="a37db-723">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-723">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-724">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-724"></span></span>|
|<span data-ttu-id="a37db-725">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-726">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-726"></span></span>|
|<span data-ttu-id="a37db-727">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-728">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-728"></span></span>|
|<span data-ttu-id="a37db-729">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-730">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-730"></span></span>|
|<span data-ttu-id="a37db-731">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-732">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-732"></span></span>|
|<span data-ttu-id="a37db-733">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-734">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-734"></span></span>|
|<span data-ttu-id="a37db-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-735">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-736">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-736"></span></span>|
|<span data-ttu-id="a37db-737">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-738">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-738"></span></span>|
   
 <span data-ttu-id="a37db-739">**GlobalSign の CA の SHA256 の G3 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="a37db-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-740">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-740">**Subject**</span></span>|
|<span data-ttu-id="a37db-741">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-741"></span></span>|
|<span data-ttu-id="a37db-742">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-742">**Issuer**</span></span>|
|<span data-ttu-id="a37db-743">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-743"></span></span>|
|<span data-ttu-id="a37db-744">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-744">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-745">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-745"></span></span>|
|<span data-ttu-id="a37db-746">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-746">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-747">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-747"></span></span>|
|<span data-ttu-id="a37db-748">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-749">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-749"></span></span>|
|<span data-ttu-id="a37db-750">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-751">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-751"></span></span>|
|<span data-ttu-id="a37db-752">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-752">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-753">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-753"></span></span>|
|<span data-ttu-id="a37db-754">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-755">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-755"></span></span>|
|<span data-ttu-id="a37db-756">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-757">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-757"></span></span>|
|<span data-ttu-id="a37db-758">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-759">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-759"></span></span>|
|<span data-ttu-id="a37db-760">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-761">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-761"></span></span>|
|<span data-ttu-id="a37db-762">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-763">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-763"></span></span>|
|<span data-ttu-id="a37db-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-764">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-765">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-765"></span></span>|
|<span data-ttu-id="a37db-766">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-767">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-767"></span></span>|
   
 <span data-ttu-id="a37db-768">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a37db-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-769">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-769">**Subject**</span></span>|
|<span data-ttu-id="a37db-770">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-770"></span></span>|
|<span data-ttu-id="a37db-771">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-771">**Issuer**</span></span>|
|<span data-ttu-id="a37db-772">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-772"></span></span>|
|<span data-ttu-id="a37db-773">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-773">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-774">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-774"></span></span>|
|<span data-ttu-id="a37db-775">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-775">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-776">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-776"></span></span>|
|<span data-ttu-id="a37db-777">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-778">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-778"></span></span>|
|<span data-ttu-id="a37db-779">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-780">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-780"></span></span>|
|<span data-ttu-id="a37db-781">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-781">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-782">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-782"></span></span>|
|<span data-ttu-id="a37db-783">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-784">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-784"></span></span>|
|<span data-ttu-id="a37db-785">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-786">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-786"></span></span>|
|<span data-ttu-id="a37db-787">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-788">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-788"></span></span>|
|<span data-ttu-id="a37db-789">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-790">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-790"></span></span>|
|<span data-ttu-id="a37db-791">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-792">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-792"></span></span>|
|<span data-ttu-id="a37db-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-793">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-794">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-794"></span></span>|
|<span data-ttu-id="a37db-795">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-796">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-796"></span></span>|
   
 <span data-ttu-id="a37db-797">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a37db-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-798">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-798">**Subject**</span></span>|
|<span data-ttu-id="a37db-799">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-799"></span></span>|
|<span data-ttu-id="a37db-800">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-800">**Issuer**</span></span>|
|<span data-ttu-id="a37db-801">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-801"></span></span>|
|<span data-ttu-id="a37db-802">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-802">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-803">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-803"></span></span>|
|<span data-ttu-id="a37db-804">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-804">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-805">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-805"></span></span>|
|<span data-ttu-id="a37db-806">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-807">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-807"></span></span>|
|<span data-ttu-id="a37db-808">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-809">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-809"></span></span>|
|<span data-ttu-id="a37db-810">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-810">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-811">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-811"></span></span>|
|<span data-ttu-id="a37db-812">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-813">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-813"></span></span>|
|<span data-ttu-id="a37db-814">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-815">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-815"></span></span>|
|<span data-ttu-id="a37db-816">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-817">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-817"></span></span>|
|<span data-ttu-id="a37db-818">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-819">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-819"></span></span>|
|<span data-ttu-id="a37db-820">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-821">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-821"></span></span>|
|<span data-ttu-id="a37db-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-822">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-823">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-823"></span></span>|
|<span data-ttu-id="a37db-824">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-825">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-825"></span></span>|
   
 <span data-ttu-id="a37db-826">**機関 X3 を暗号化してみましょう**</span><span class="sxs-lookup"><span data-stu-id="a37db-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-827">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-827">**Subject**</span></span>|
|<span data-ttu-id="a37db-828">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-828"></span></span>|
|<span data-ttu-id="a37db-829">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-829">**Issuer**</span></span>|
|<span data-ttu-id="a37db-830">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-830"></span></span>|
|<span data-ttu-id="a37db-831">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-831">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-832">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-832"></span></span>|
|<span data-ttu-id="a37db-833">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-833">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-834">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-834"></span></span>|
|<span data-ttu-id="a37db-835">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-836">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-836"></span></span>|
|<span data-ttu-id="a37db-837">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-838">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-838"></span></span>|
|<span data-ttu-id="a37db-839">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-839">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-840">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-840"></span></span>|
|<span data-ttu-id="a37db-841">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-842">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-842"></span></span>|
|<span data-ttu-id="a37db-843">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-844">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-844"></span></span>|
|<span data-ttu-id="a37db-845">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-846">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-846"></span></span>|
|<span data-ttu-id="a37db-847">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-848">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-848"></span></span>|
|<span data-ttu-id="a37db-849">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-850">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-850"></span></span>|
|<span data-ttu-id="a37db-851">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-851">**AIA URLs**</span></span>|
|<span data-ttu-id="a37db-852">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-852"></span></span>|
|<span data-ttu-id="a37db-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-853">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-854">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-854"></span></span>|
|<span data-ttu-id="a37db-855">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-856">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-856"></span></span>|
   
 <span data-ttu-id="a37db-857">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a37db-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-858">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-858">**Subject**</span></span>|
|<span data-ttu-id="a37db-859">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-859"></span></span>|
|<span data-ttu-id="a37db-860">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-860">**Issuer**</span></span>|
|<span data-ttu-id="a37db-861">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-861"></span></span>|
|<span data-ttu-id="a37db-862">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-862">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-863">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-863"></span></span>|
|<span data-ttu-id="a37db-864">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-864">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-865">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-865"></span></span>|
|<span data-ttu-id="a37db-866">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-867">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-867"></span></span>|
|<span data-ttu-id="a37db-868">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-869">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-869"></span></span>|
|<span data-ttu-id="a37db-870">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-870">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-871">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-871"></span></span>|
|<span data-ttu-id="a37db-872">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-873">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-873"></span></span>|
|<span data-ttu-id="a37db-874">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-875">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-875"></span></span>|
|<span data-ttu-id="a37db-876">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-877">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-877"></span></span>|
|<span data-ttu-id="a37db-878">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-879">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-879"></span></span>|
|<span data-ttu-id="a37db-880">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-881">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-881"></span></span>|
|<span data-ttu-id="a37db-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-882">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-883">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-883"></span></span>|
   
 <span data-ttu-id="a37db-884">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a37db-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-885">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-885">**Subject**</span></span>|
|<span data-ttu-id="a37db-886">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-886"></span></span>|
|<span data-ttu-id="a37db-887">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-887">**Issuer**</span></span>|
|<span data-ttu-id="a37db-888">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-888"></span></span>|
|<span data-ttu-id="a37db-889">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-889">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-890">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-890"></span></span>|
|<span data-ttu-id="a37db-891">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-891">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-892">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-892"></span></span>|
|<span data-ttu-id="a37db-893">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-894">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-894"></span></span>|
|<span data-ttu-id="a37db-895">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-896">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-896"></span></span>|
|<span data-ttu-id="a37db-897">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-897">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-898">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-898"></span></span>|
|<span data-ttu-id="a37db-899">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-900">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-900"></span></span>|
|<span data-ttu-id="a37db-901">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-902">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-902"></span></span>|
|<span data-ttu-id="a37db-903">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-904">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-904"></span></span>|
|<span data-ttu-id="a37db-905">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-906">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-906"></span></span>|
|<span data-ttu-id="a37db-907">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-908">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-908"></span></span>|
|<span data-ttu-id="a37db-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-909">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-910">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-910"></span></span>|
|<span data-ttu-id="a37db-911">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-912">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-912"></span></span>|
   
 <span data-ttu-id="a37db-913">**Microsoft IT の TLS の CA 1**</span><span class="sxs-lookup"><span data-stu-id="a37db-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-914">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-914">**Subject**</span></span>|
|<span data-ttu-id="a37db-915">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-915"></span></span>|
|<span data-ttu-id="a37db-916">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-916">**Issuer**</span></span>|
|<span data-ttu-id="a37db-917">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-917"></span></span>|
|<span data-ttu-id="a37db-918">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-918">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-919">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-919"></span></span>|
|<span data-ttu-id="a37db-920">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-920">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-921">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-921"></span></span>|
|<span data-ttu-id="a37db-922">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-923">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-923"></span></span>|
|<span data-ttu-id="a37db-924">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-925">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-925"></span></span>|
|<span data-ttu-id="a37db-926">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-926">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-927">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-927"></span></span>|
|<span data-ttu-id="a37db-928">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-929">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-929"></span></span>|
|<span data-ttu-id="a37db-930">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-931">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-931"></span></span>|
|<span data-ttu-id="a37db-932">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-933">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-933"></span></span>|
|<span data-ttu-id="a37db-934">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-935">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-935"></span></span>|
|<span data-ttu-id="a37db-936">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-937">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-937"></span></span>|
|<span data-ttu-id="a37db-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-938">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-939">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-939"></span></span>|
|<span data-ttu-id="a37db-940">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-941">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-941"></span></span>|
   
 <span data-ttu-id="a37db-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="a37db-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-943">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-943">**Subject**</span></span>|
|<span data-ttu-id="a37db-944">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-944"></span></span>|
|<span data-ttu-id="a37db-945">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-945">**Issuer**</span></span>|
|<span data-ttu-id="a37db-946">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-946"></span></span>|
|<span data-ttu-id="a37db-947">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-947">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-948">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-948"></span></span>|
|<span data-ttu-id="a37db-949">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-949">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-950">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-950"></span></span>|
|<span data-ttu-id="a37db-951">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-952">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-952"></span></span>|
|<span data-ttu-id="a37db-953">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-954">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-954"></span></span>|
|<span data-ttu-id="a37db-955">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-955">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-956">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-956"></span></span>|
|<span data-ttu-id="a37db-957">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-958">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-958"></span></span>|
|<span data-ttu-id="a37db-959">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-960">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-960"></span></span>|
|<span data-ttu-id="a37db-961">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-962">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-962"></span></span>|
|<span data-ttu-id="a37db-963">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-964">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-964"></span></span>|
|<span data-ttu-id="a37db-965">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-966">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-966"></span></span>|
|<span data-ttu-id="a37db-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-967">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-968">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-968"></span></span>|
|<span data-ttu-id="a37db-969">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-970">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-970"></span></span>|
   
 <span data-ttu-id="a37db-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="a37db-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-972">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-972">**Subject**</span></span>|
|<span data-ttu-id="a37db-973">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-973"></span></span>|
|<span data-ttu-id="a37db-974">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-974">**Issuer**</span></span>|
|<span data-ttu-id="a37db-975">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-975"></span></span>|
|<span data-ttu-id="a37db-976">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-976">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-977">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-977"></span></span>|
|<span data-ttu-id="a37db-978">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-978">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-979">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-979"></span></span>|
|<span data-ttu-id="a37db-980">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-981">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-981"></span></span>|
|<span data-ttu-id="a37db-982">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-983">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-983"></span></span>|
|<span data-ttu-id="a37db-984">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-984">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-985">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-985"></span></span>|
|<span data-ttu-id="a37db-986">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-987">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-987"></span></span>|
|<span data-ttu-id="a37db-988">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-989">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-989"></span></span>|
|<span data-ttu-id="a37db-990">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-991">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-991"></span></span>|
|<span data-ttu-id="a37db-992">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-993">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-993"></span></span>|
|<span data-ttu-id="a37db-994">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-995">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-995"></span></span>|
|<span data-ttu-id="a37db-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-996">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-997">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-997"></span></span>|
|<span data-ttu-id="a37db-998">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-999">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-999"></span></span>|
   
 <span data-ttu-id="a37db-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="a37db-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-1001">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1001">**Subject**</span></span>|
|<span data-ttu-id="a37db-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1002"></span></span>|
|<span data-ttu-id="a37db-1003">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-1003">**Issuer**</span></span>|
|<span data-ttu-id="a37db-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1004"></span></span>|
|<span data-ttu-id="a37db-1005">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-1005">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1006"></span></span>|
|<span data-ttu-id="a37db-1007">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1008"></span></span>|
|<span data-ttu-id="a37db-1009">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1010"></span></span>|
|<span data-ttu-id="a37db-1011">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1012"></span></span>|
|<span data-ttu-id="a37db-1013">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1014"></span></span>|
|<span data-ttu-id="a37db-1015">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1016"></span></span>|
|<span data-ttu-id="a37db-1017">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1018"></span></span>|
|<span data-ttu-id="a37db-1019">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1020"></span></span>|
|<span data-ttu-id="a37db-1021">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1022"></span></span>|
|<span data-ttu-id="a37db-1023">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1024"></span></span>|
|<span data-ttu-id="a37db-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1026"></span></span>|
|<span data-ttu-id="a37db-1027">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1028"></span></span>|
   
 <span data-ttu-id="a37db-1029">**Symantec クラス 3 の EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="a37db-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-1030">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1030">**Subject**</span></span>|
|<span data-ttu-id="a37db-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1031"></span></span>|
|<span data-ttu-id="a37db-1032">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-1032">**Issuer**</span></span>|
|<span data-ttu-id="a37db-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1033"></span></span>|
|<span data-ttu-id="a37db-1034">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a37db-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1035"></span></span>|
|<span data-ttu-id="a37db-1036">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-1036">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1037"></span></span>|
|<span data-ttu-id="a37db-1038">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1039"></span></span>|
|<span data-ttu-id="a37db-1040">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1041"></span></span>|
|<span data-ttu-id="a37db-1042">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1043"></span></span>|
|<span data-ttu-id="a37db-1044">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1045"></span></span>|
|<span data-ttu-id="a37db-1046">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1047"></span></span>|
|<span data-ttu-id="a37db-1048">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1049"></span></span>|
|<span data-ttu-id="a37db-1050">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1051"></span></span>|
|<span data-ttu-id="a37db-1052">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1053"></span></span>|
|<span data-ttu-id="a37db-1054">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1055"></span></span>|
|<span data-ttu-id="a37db-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1057"></span></span>|
|<span data-ttu-id="a37db-1058">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1059"></span></span>|
   
 <span data-ttu-id="a37db-1060">**Symantec クラス 3 セキュリティで保護されたサーバー CA - 第 4 世代**</span><span class="sxs-lookup"><span data-stu-id="a37db-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-1061">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1061">**Subject**</span></span>|
|<span data-ttu-id="a37db-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1062"></span></span>|
|<span data-ttu-id="a37db-1063">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-1063">**Issuer**</span></span>|
|<span data-ttu-id="a37db-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1064"></span></span>|
|<span data-ttu-id="a37db-1065">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a37db-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1066"></span></span>|
|<span data-ttu-id="a37db-1067">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-1067">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1068"></span></span>|
|<span data-ttu-id="a37db-1069">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1070"></span></span>|
|<span data-ttu-id="a37db-1071">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1072"></span></span>|
|<span data-ttu-id="a37db-1073">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1074"></span></span>|
|<span data-ttu-id="a37db-1075">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1076"></span></span>|
|<span data-ttu-id="a37db-1077">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1078"></span></span>|
|<span data-ttu-id="a37db-1079">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1080"></span></span>|
|<span data-ttu-id="a37db-1081">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1082"></span></span>|
|<span data-ttu-id="a37db-1083">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1084"></span></span>|
|<span data-ttu-id="a37db-1085">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1086"></span></span>|
|<span data-ttu-id="a37db-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1088"></span></span>|
|<span data-ttu-id="a37db-1089">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1090"></span></span>|
   
 <span data-ttu-id="a37db-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="a37db-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-1092">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1092">**Subject**</span></span>|
|<span data-ttu-id="a37db-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1093"></span></span>|
|<span data-ttu-id="a37db-1094">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-1094">**Issuer**</span></span>|
|<span data-ttu-id="a37db-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1095"></span></span>|
|<span data-ttu-id="a37db-1096">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a37db-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1097"></span></span>|
|<span data-ttu-id="a37db-1098">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-1098">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1099"></span></span>|
|<span data-ttu-id="a37db-1100">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1101"></span></span>|
|<span data-ttu-id="a37db-1102">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1103"></span></span>|
|<span data-ttu-id="a37db-1104">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1105"></span></span>|
|<span data-ttu-id="a37db-1106">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1107"></span></span>|
|<span data-ttu-id="a37db-1108">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1109"></span></span>|
|<span data-ttu-id="a37db-1110">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1111"></span></span>|
|<span data-ttu-id="a37db-1112">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1113"></span></span>|
|<span data-ttu-id="a37db-1114">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1115"></span></span>|
|<span data-ttu-id="a37db-1116">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1117"></span></span>|
|<span data-ttu-id="a37db-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1119"></span></span>|
|<span data-ttu-id="a37db-1120">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1121"></span></span>|
   
 <span data-ttu-id="a37db-1122">**Verizon akamai 社 SureServer CA G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="a37db-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a37db-1123">**件名**</span><span class="sxs-lookup"><span data-stu-id="a37db-1123">**Subject**</span></span>|
|<span data-ttu-id="a37db-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1124"></span></span>|
|<span data-ttu-id="a37db-1125">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a37db-1125">**Issuer**</span></span>|
|<span data-ttu-id="a37db-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1126"></span></span>|
|<span data-ttu-id="a37db-1127">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a37db-1127">**Serial Number**</span></span>|
|<span data-ttu-id="a37db-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1128"></span></span>|
|<span data-ttu-id="a37db-1129">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a37db-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="a37db-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1130"></span></span>|
|<span data-ttu-id="a37db-1131">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a37db-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a37db-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1132"></span></span>|
|<span data-ttu-id="a37db-1133">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a37db-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="a37db-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1134"></span></span>|
|<span data-ttu-id="a37db-1135">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a37db-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="a37db-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1136"></span></span>|
|<span data-ttu-id="a37db-1137">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1138"></span></span>|
|<span data-ttu-id="a37db-1139">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a37db-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a37db-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1140"></span></span>|
|<span data-ttu-id="a37db-1141">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a37db-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1142"></span></span>|
|<span data-ttu-id="a37db-1143">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1144"></span></span>|
|<span data-ttu-id="a37db-1145">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a37db-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a37db-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1146"></span></span>|
|<span data-ttu-id="a37db-1147">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="a37db-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1148"></span></span>|
|<span data-ttu-id="a37db-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="a37db-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1150"></span></span>|
|<span data-ttu-id="a37db-1151">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a37db-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="a37db-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="a37db-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="a37db-1153">追加の証明書のパス</span><span class="sxs-lookup"><span data-stu-id="a37db-1153">Additional certificate paths</span></span>
<span data-ttu-id="a37db-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a37db-1154"></span></span>

<span data-ttu-id="a37db-1155">次には、上は含まれていないし、時間の経過と共に上のリストと結合されている従来の証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a37db-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


